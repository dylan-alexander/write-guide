---
Description: Posted to an application when a user cancels the application's journaling activities. The message is posted with a NULL window handle.
ms.assetid: 7515acb5-4526-40f7-abb7-822a073ac7dc
title: WM_CANCELJOURNAL message (Winuser.h)
ms.topic: reference
ms.date: 05/31/2018
---

# WM\_CANCELJOURNAL message

Posted to an application when a user cancels the application's journaling activities. The message is posted with a **NULL** window handle.


```C++
#define WM_CANCELJOURNAL                0x004B
```



## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

This parameter is not used.

</dd> <dt>

*lParam* 
</dt> <dd>

This parameter is not used.

</dd> </dl>

## Return value

Type: **void**

This message does not return a value. It is meant to be processed from within an application's main loop or a [**GetMessage**](https://msdn.microsoft.com/en-us/library/ms644936(v=VS.85).aspx) hook procedure, not from a window procedure.

## Remarks

Journal record and playback modes are modes imposed on the system that let an application sequentially record or play back user input. The system enters these modes when an application installs a [*JournalRecordProc*](https://msdn.microsoft.com/en-us/library/ms644983(v=VS.85).aspx) or [*JournalPlaybackProc*](https://msdn.microsoft.com/en-us/library/ms644982(v=VS.85).aspx) hook procedure. When the system is in either of these journaling modes, applications must take turns reading input from the input queue. If any one application stops reading input while the system is in a journaling mode, other applications are forced to wait.

To ensure a robust system, one that cannot be made unresponsive by any one application, the system automatically cancels any journaling activities when a user presses CTRL+ESC or CTRL+ALT+DEL. The system then unhooks any journaling hook procedures, and posts a **WM\_CANCELJOURNAL** message, with a **NULL** window handle, to the application that set the journaling hook.

The **WM\_CANCELJOURNAL** message has a **NULL** window handle, therefore it cannot be dispatched to a window procedure. There are two ways for an application to see a **WM\_CANCELJOURNAL** message: If the application is running in its own main loop, it must catch the message between its call to [**GetMessage**](https://msdn.microsoft.com/en-us/library/ms644936(v=VS.85).aspx) or [**PeekMessage**](https://msdn.microsoft.com/en-us/library/ms644943(v=VS.85).aspx) and its call to [**DispatchMessage**](https://msdn.microsoft.com/en-us/library/ms644934(v=VS.85).aspx). If the application is not running in its own main loop, it must set a [*GetMsgProc*](https://msdn.microsoft.com/en-us/library/ms644981(v=VS.85).aspx) hook procedure (through a call to [**SetWindowsHookEx**](https://msdn.microsoft.com/en-us/library/ms644990(v=VS.85).aspx) specifying the **WH\_GETMESSAGE** hook type) that watches for the message.

When an application sees a **WM\_CANCELJOURNAL** message, it can assume two things: the user has intentionally canceled the journal record or playback mode, and the system has already unhooked any journal record or playback hook procedures.

Note that the key combinations mentioned above (CTRL+ESC or CTRL+ALT+DEL) cause the system to cancel journaling. If any one application is made unresponsive, they give the user a means of recovery. The [**VK\_CANCEL**](https://msdn.microsoft.com/en-us/library/Dd375731(v=VS.85).aspx) virtual key code (usually implemented as the CTRL+BREAK key combination) is what an application that is in journal record mode should watch for as a signal that the user wishes to cancel the journaling activity. The difference is that watching for **VK\_CANCEL** is a suggested behavior for journaling applications, whereas CTRL+ESC or CTRL+ALT+DEL cause the system to cancel journaling regardless of a journaling application's behavior.

## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                                               |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Winuser.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

**Reference**
</dt> <dt>

[*JournalPlaybackProc*](https://msdn.microsoft.com/en-us/library/ms644982(v=VS.85).aspx)
</dt> <dt>

[*JournalRecordProc*](https://msdn.microsoft.com/en-us/library/ms644983(v=VS.85).aspx)
</dt> <dt>

[*GetMsgProc*](https://msdn.microsoft.com/en-us/library/ms644981(v=VS.85).aspx)
</dt> <dt>

[**SetWindowsHookEx**](https://msdn.microsoft.com/en-us/library/ms644990(v=VS.85).aspx)
</dt> <dt>

**Conceptual**
</dt> <dt>

[Hooks](hooks.md)
</dt> </dl>

 

 




