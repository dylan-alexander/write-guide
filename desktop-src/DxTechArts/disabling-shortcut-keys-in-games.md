---
title: Disabling Shortcut Keys in Games
description: This articles describes how to temporarily disable keyboard shortcuts in Microsoft Windows to prevent disruption of game play for full screen games.
ms.assetid: 732523f9-ecff-c6c2-646d-1bc3443232ab
ms.topic: article
ms.date: 05/31/2018
---

# Disabling Shortcut Keys in Games

This articles describes how to temporarily disable keyboard shortcuts in Microsoft Windows to prevent disruption of game play for full screen games. The SHIFT key and the CTRL key are often used as fire or run buttons in games. If users accidentally press the Windows key (located near these keys), they can cause themselves to suddenly jump out of the application, which ruins the game experience. Simply using the SHIFT key as a game button can inadvertently execute the StickyKeys shortcut which may display a warning dialog. To avoid these issues, you should disable these keys when running in full-screen mode, and either enable the keys back to their default handlers when running in windowed mode or exit the application.

This article describes how to do the following:

-   [Disable the Windows Key with a Keyboard Hook](#disable-the-windows-key-with-a-keyboard-hook)
-   [Disable the Accessibility Shortcut Keys](#disable-the-accessibility-shortcut-keys)

## Disable the Windows Key with a Keyboard Hook

Use a low-level keyboard hook to filter out the Windows key from being processed. The low-level keyboard hook shown in Example 1 remains in effect even if a user minimizes the window or switches to another application. This means that you must be careful to ensure that the Windows key is not disabled when the application is deactivated. The code in Example 1 does this by handling the WM\_ACTIVATEAPP message.

> [!Note]  
> This method works on Windows 2000 and later versions of Windows. This method also works with least-privileged user accounts (also known as limited-user accounts).

 

This method is used by DXUT and is illustrated in the following code example.

**Example 1. Using a low-level keyboard hook to disable the Windows key**


```C++
HHOOK g_hKeyboardHook;
BOOL g_bFullscreen;
 
INT WINAPI WinMain( HINSTANCE, HINSTANCE, LPSTR, int )
{
    // Initialization
    g_hKeyboardHook = SetWindowsHookEx( WH_KEYBOARD_LL,  LowLevelKeyboardProc, GetModuleHandle(NULL), 0 );
 
    // 
    // main application code here
    // 
 
    // Cleanup before shutdown
    UnhookWindowsHookEx( g_hKeyboardHook );
}
 
 
LRESULT CALLBACK LowLevelKeyboardProc( int nCode, WPARAM wParam, LPARAM lParam )
{
    if (nCode < 0 || nCode != HC_ACTION )  // do not process message 
        return CallNextHookEx( g_hKeyboardHook, nCode, wParam, lParam); 
 
    bool bEatKeystroke = false;
    KBDLLHOOKSTRUCT* p = (KBDLLHOOKSTRUCT*)lParam;
    switch (wParam) 
    {
        case WM_KEYDOWN:  
        case WM_KEYUP:    
        {
            bEatKeystroke = (g_bFullscreen && g_bWindowActive && ((p->vkCode == VK_LWIN) || (p->vkCode == VK_RWIN)));
            break;
        }
    }
 
    if( bEatKeystroke )
        return 1;
    else
        return CallNextHookEx( g_hKeyboardHook, nCode, wParam, lParam );
}
 
 
LRESULT CALLBACK WndProc( HWND hWnd, UINT uMsg, WPARAM wParam, LPARAM lParam )
{
    switch( uMsg )
    {
       case WM_ACTIVATEAPP:
            // g_bWindowActive is used to control if the Windows key is filtered by the keyboard hook or not.
            if( wParam == TRUE )
                g_bWindowActive  = true;           
            else 
                g_bWindowActive  = false;           
            break;
    }
}
```



## Disable the Accessibility Shortcut Keys

Windows includes accessibility features such as StickyKeys, FilterKeys, and ToggleKeys (see [Windows Accessibility](https://msdn.microsoft.com/library/Aa227589(v=VS.60).aspx)). Each of these serves a different purpose; StickyKeys for example, is designed for people who have difficulty holding down two or more keys simultaneously. Each of these accessibility features also has a keyboard shortcut that allows the feature to be turned on or off. For example, the StickyKeys shortcut is triggered by pressing the SHIFT key five times. If the SHIFT key is also used in the game, the user could accidentally trigger this shortcut during game play. When the shortcut is triggered, Windows (by default) presents a warning in a dialog box, which would cause Windows to minimize a game running in full-screen mode. This, of course, can have a drastic effect on game play.

The accessibility features are required for some customers and do not themselves interfere with full-screen games; therefore, you should not change the accessibility settings. However, because the shortcuts for accessibility features can disrupt game play if triggered accidentally, you should turn off an accessibility shortcut only when that feature is not enabled by calling [**SystemParametersInfo**](https://msdn.microsoft.com/library/Aa227580(v=VS.60).aspx).

An accessibility shortcut that is turned off by [**SystemParametersInfo**](https://msdn.microsoft.com/library/Aa227580(v=VS.60).aspx) remains turned off even after the application has exited. This means that you must restore the settings before exiting the application. Because it is possible for the application to fail to exit correctly, you should write these settings to persistent storage so that they can be restored when the application is run again. You could also use an exception handler to restore these settings if a crash occurs.

**To turn off these shortcuts**

1.  Capture the current accessibility settings before disabling them.
2.  Disable the accessibility shortcut when the application goes into full-screen mode if the accessibility feature is off.
3.  Restore the accessibility settings when the application goes into windowed mode or exits.

This method is used in DXUT, and is illustrated in the following code example.

> [!Note]  
> This method works when running on a limited user account.

 

**Example 2. Disabling accessibility shortcut keys**


```C++
STICKYKEYS g_StartupStickyKeys = {sizeof(STICKYKEYS), 0};
TOGGLEKEYS g_StartupToggleKeys = {sizeof(TOGGLEKEYS), 0};
FILTERKEYS g_StartupFilterKeys = {sizeof(FILTERKEYS), 0};    
 
 
INT WINAPI WinMain( HINSTANCE, HINSTANCE, LPSTR, int )
{
    // Save the current sticky/toggle/filter key settings so they can be restored them later
    SystemParametersInfo(SPI_GETSTICKYKEYS, sizeof(STICKYKEYS), &g_StartupStickyKeys, 0);
    SystemParametersInfo(SPI_GETTOGGLEKEYS, sizeof(TOGGLEKEYS), &g_StartupToggleKeys, 0);
    SystemParametersInfo(SPI_GETFILTERKEYS, sizeof(FILTERKEYS), &g_StartupFilterKeys, 0);
 
    // Disable when full screen
    AllowAccessibilityShortcutKeys( true );
 
    // Restore back when going to windowed or shutting down
    AllowAccessibilityShortcutKeys( false );
}
 
 
void AllowAccessibilityShortcutKeys( bool bAllowKeys )
{
    if( bAllowKeys )
    {
        // Restore StickyKeys/etc to original state and enable Windows key      
        STICKYKEYS sk = g_StartupStickyKeys;
        TOGGLEKEYS tk = g_StartupToggleKeys;
        FILTERKEYS fk = g_StartupFilterKeys;
        
        SystemParametersInfo(SPI_SETSTICKYKEYS, sizeof(STICKYKEYS), &g_StartupStickyKeys, 0);
        SystemParametersInfo(SPI_SETTOGGLEKEYS, sizeof(TOGGLEKEYS), &g_StartupToggleKeys, 0);
        SystemParametersInfo(SPI_SETFILTERKEYS, sizeof(FILTERKEYS), &g_StartupFilterKeys, 0);
    }
    else
    {
        // Disable StickyKeys/etc shortcuts but if the accessibility feature is on, 
        // then leave the settings alone as its probably being usefully used
 
        STICKYKEYS skOff = g_StartupStickyKeys;
        if( (skOff.dwFlags & SKF_STICKYKEYSON) == 0 )
        {
            // Disable the hotkey and the confirmation
            skOff.dwFlags &= ~SKF_HOTKEYACTIVE;
            skOff.dwFlags &= ~SKF_CONFIRMHOTKEY;
 
            SystemParametersInfo(SPI_SETSTICKYKEYS, sizeof(STICKYKEYS), &skOff, 0);
        }
 
        TOGGLEKEYS tkOff = g_StartupToggleKeys;
        if( (tkOff.dwFlags & TKF_TOGGLEKEYSON) == 0 )
        {
            // Disable the hotkey and the confirmation
            tkOff.dwFlags &= ~TKF_HOTKEYACTIVE;
            tkOff.dwFlags &= ~TKF_CONFIRMHOTKEY;
 
            SystemParametersInfo(SPI_SETTOGGLEKEYS, sizeof(TOGGLEKEYS), &tkOff, 0);
        }
 
        FILTERKEYS fkOff = g_StartupFilterKeys;
        if( (fkOff.dwFlags & FKF_FILTERKEYSON) == 0 )
        {
            // Disable the hotkey and the confirmation
            fkOff.dwFlags &= ~FKF_HOTKEYACTIVE;
            fkOff.dwFlags &= ~FKF_CONFIRMHOTKEY;
 
            SystemParametersInfo(SPI_SETFILTERKEYS, sizeof(FILTERKEYS), &fkOff, 0);
        }
    }
}
```



 

 




