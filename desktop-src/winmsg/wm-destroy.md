---
Description: Sent when a window is being destroyed. It is sent to the window procedure of the window being destroyed after the window is removed from the screen.
ms.assetid: 089c0645-199b-4a90-9cbc-740f0cf3267d
title: WM_DESTROY message (Winuser.h)
ms.topic: reference
ms.date: 05/31/2018
---

# WM\_DESTROY message

Sent when a window is being destroyed. It is sent to the window procedure of the window being destroyed after the window is removed from the screen.

This message is sent first to the window being destroyed and then to the child windows (if any) as they are destroyed. During the processing of the message, it can be assumed that all child windows still exist.

A window receives this message through its [**WindowProc**](https://msdn.microsoft.com/en-us/library/ms633573(v=VS.85).aspx) function.


```C++
#define WM_DESTROY                      0x0002
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

Type: **LRESULT**

If an application processes this message, it should return zero.

## Remarks

If the window being destroyed is part of the clipboard viewer chain (set by calling the [**SetClipboardViewer**](https://msdn.microsoft.com/en-us/library/ms649052(v=VS.85).aspx) function), the window must remove itself from the chain by processing the [**ChangeClipboardChain**](https://msdn.microsoft.com/en-us/library/ms649034(v=VS.85).aspx) function before returning from the **WM\_DESTROY** message.

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

[**ChangeClipboardChain**](https://msdn.microsoft.com/en-us/library/ms649034(v=VS.85).aspx)
</dt> <dt>

[**DestroyWindow**](https://msdn.microsoft.com/en-us/library/ms632682(v=VS.85).aspx)
</dt> <dt>

[**PostQuitMessage**](https://msdn.microsoft.com/en-us/library/ms644945(v=VS.85).aspx)
</dt> <dt>

[**SetClipboardViewer**](https://msdn.microsoft.com/en-us/library/ms649052(v=VS.85).aspx)
</dt> <dt>

[**WM\_CLOSE**](wm-close.md)
</dt> <dt>

**Conceptual**
</dt> <dt>

[Windows](windows.md)
</dt> </dl>

 

 




