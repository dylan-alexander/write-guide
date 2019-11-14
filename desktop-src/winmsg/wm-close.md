---
Description: Sent as a signal that a window or an application should terminate.
ms.assetid: 19500baf-e0ad-4dfa-804f-6a6e0652cffb
title: WM_CLOSE message (Winuser.h)
ms.topic: reference
ms.date: 05/31/2018
---

# WM\_CLOSE message

Sent as a signal that a window or an application should terminate.

A window receives this message through its [**WindowProc**](https://msdn.microsoft.com/en-us/library/ms633573(v=VS.85).aspx) function.


```C++
#define WM_CLOSE                        0x0010
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

An application can prompt the user for confirmation, prior to destroying a window, by processing the **WM\_CLOSE** message and calling the [**DestroyWindow**](https://msdn.microsoft.com/en-us/library/ms632682(v=VS.85).aspx) function only if the user confirms the choice.

By default, the [**DefWindowProc**](https://msdn.microsoft.com/en-us/library/ms633572(v=VS.85).aspx) function calls the [**DestroyWindow**](https://msdn.microsoft.com/en-us/library/ms632682(v=VS.85).aspx) function to destroy the window.

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

[**DefWindowProc**](https://msdn.microsoft.com/en-us/library/ms633572(v=VS.85).aspx)
</dt> <dt>

[**DestroyWindow**](https://msdn.microsoft.com/en-us/library/ms632682(v=VS.85).aspx)
</dt> <dt>

**Conceptual**
</dt> <dt>

[Windows](windows.md)
</dt> </dl>

 

 




