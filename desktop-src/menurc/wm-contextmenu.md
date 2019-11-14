---
title: WM_CONTEXTMENU message (Winuser.h)
description: Notifies a window that the user clicked the right mouse button (right-clicked) in the window.
ms.assetid: e607a61a-0f9b-4d11-b8c0-b01a2e7fb35b
keywords:
- WM_CONTEXTMENU message Menus and Other Resources
topic_type:
- apiref
api_name:
- WM_CONTEXTMENU
api_location:
- Winuser.h
api_type:
- HeaderDef
ms.topic: reference
ms.date: 05/31/2018
---

# WM\_CONTEXTMENU message

Notifies a window that the user clicked the right mouse button (right-clicked) in the window.


```C++
#define WM_CONTEXTMENU                  0x007B
```



## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

A handle to the window in which the user right-clicked the mouse. This can be a child window of the window receiving the message. For more information about processing this message, see the Remarks section.

</dd> <dt>

*lParam* 
</dt> <dd>

The low-order word specifies the horizontal position of the cursor, in screen coordinates, at the time of the mouse click.

The high-order word specifies the vertical position of the cursor, in screen coordinates, at the time of the mouse click.

</dd> </dl>

## Return value

No return value.

## Remarks

A window can process this message by displaying a shortcut menu using the [**TrackPopupMenu**](/windows/desktop/api/Winuser/nf-winuser-trackpopupmenu) or [**TrackPopupMenuEx**](/windows/desktop/api/Winuser/nf-winuser-trackpopupmenuex) functions. To obtain the horizontal and vertical positions, use the following code.


```
xPos = GET_X_LPARAM(lParam); 
yPos = GET_Y_LPARAM(lParam); 
```



If a window does not display a shortcut menu it should pass this message to the [**DefWindowProc**](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-defwindowproca) function. If a window is a child window, **DefWindowProc** sends the message to the parent. Otherwise, **DefWindowProc** displays a default shortcut menu if the specified position is in the window's caption.

[**DefWindowProc**](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-defwindowproca) generates the **WM\_CONTEXTMENU** message when it processes the [**WM\_RBUTTONUP**](https://docs.microsoft.com/windows/desktop/inputdev/wm-rbuttonup) or [**WM\_NCRBUTTONUP**](https://docs.microsoft.com/windows/desktop/inputdev/wm-ncrbuttonup) message or when the user types SHIFT+F10. The **WM\_CONTEXTMENU** message is also generated when the user presses and releases the [**VK\_APPS**](https://docs.microsoft.com/windows/desktop/inputdev/virtual-key-codes) key.

If the context menu is generated from the keyboard for example, if the user types SHIFT+F10 then the x- and y-coordinates are -1 and the application should display the context menu at the location of the current selection rather than at (xPos, yPos).

## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                                               |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Winuser.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

**Reference**
</dt> <dt>

[**DefWindowProc**](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-defwindowproca)
</dt> <dt>

[**GET\_X\_LPARAM**](https://docs.microsoft.com/windows/desktop/api/windowsx/nf-windowsx-get_x_lparam)
</dt> <dt>

[**GET\_Y\_LPARAM**](https://docs.microsoft.com/windows/desktop/api/windowsx/nf-windowsx-get_y_lparam)
</dt> <dt>

[**TrackPopupMenu**](/windows/desktop/api/Winuser/nf-winuser-trackpopupmenu)
</dt> <dt>

[**TrackPopupMenuEx**](/windows/desktop/api/Winuser/nf-winuser-trackpopupmenuex)
</dt> <dt>

[**WM\_NCRBUTTONUP**](https://docs.microsoft.com/windows/desktop/inputdev/wm-ncrbuttonup)
</dt> <dt>

[**WM\_RBUTTONUP**](https://docs.microsoft.com/windows/desktop/inputdev/wm-rbuttonup)
</dt> <dt>

**Conceptual**
</dt> <dt>

[Menus](menus.md)
</dt> </dl>

 

 





