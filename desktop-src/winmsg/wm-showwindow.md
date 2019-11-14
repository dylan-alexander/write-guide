---
Description: Sent to a window when the window is about to be hidden or shown.
ms.assetid: dea7c9aa-eba7-4b93-a4c5-9b2d36999780
title: WM_SHOWWINDOW message (Winuser.h)
ms.topic: reference
ms.date: 05/31/2018
---

# WM\_SHOWWINDOW message

Sent to a window when the window is about to be hidden or shown.

A window receives this message through its [**WindowProc**](https://msdn.microsoft.com/en-us/library/ms633573(v=VS.85).aspx) function.


```C++
#define WM_SHOWWINDOW                   0x0018
```



## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

Indicates whether a window is being shown. If *wParam* is **TRUE**, the window is being shown. If *wParam* is **FALSE**, the window is being hidden.

</dd> <dt>

*lParam* 
</dt> <dd>

The status of the window being shown. If *lParam* is zero, the message was sent because of a call to the [**ShowWindow**](https://msdn.microsoft.com/en-us/library/ms633548(v=VS.85).aspx) function; otherwise, *lParam* is one of the following values.



| Value                                                                                                                                                                                                                         | Meaning                                                                                       |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| <span id="SW_OTHERUNZOOM"></span><span id="sw_otherunzoom"></span><dl> <dt>**SW\_OTHERUNZOOM**</dt> <dt>4</dt> </dl>       | The window is being uncovered because a maximize window was restored or minimized.<br/> |
| <span id="SW_OTHERZOOM"></span><span id="sw_otherzoom"></span><dl> <dt>**SW\_OTHERZOOM**</dt> <dt>2</dt> </dl>             | The window is being covered by another window that has been maximized.<br/>             |
| <span id="SW_PARENTCLOSING"></span><span id="sw_parentclosing"></span><dl> <dt>**SW\_PARENTCLOSING**</dt> <dt>1</dt> </dl> | The window's owner window is being minimized.<br/>                                      |
| <span id="SW_PARENTOPENING"></span><span id="sw_parentopening"></span><dl> <dt>**SW\_PARENTOPENING**</dt> <dt>3</dt> </dl> | The window's owner window is being restored.<br/>                                       |



 

</dd> </dl>

## Return value

Type: **LRESULT**

If an application processes this message, it should return zero.

## Remarks

The [**DefWindowProc**](https://msdn.microsoft.com/en-us/library/ms633572(v=VS.85).aspx) function hides or shows the window, as specified by the message. If a window has the [**WS\_VISIBLE**](window-styles.md) style when it is created, the window receives this message after it is created, but before it is displayed. A window also receives this message when its visibility state is changed by the [**ShowWindow**](https://msdn.microsoft.com/en-us/library/ms633548(v=VS.85).aspx) or [**ShowOwnedPopups**](https://msdn.microsoft.com/en-us/library/ms633547(v=VS.85).aspx) function.

The **WM\_SHOWWINDOW** message is not sent under the following circumstances:

-   When a top-level, overlapped window is created with the [**WS\_MAXIMIZE**](window-styles.md) or **WS\_MINIMIZE** style.
-   When the **SW\_SHOWNORMAL** flag is specified in the call to the [**ShowWindow**](https://msdn.microsoft.com/en-us/library/ms633548(v=VS.85).aspx) function.

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

[**ShowOwnedPopups**](https://msdn.microsoft.com/en-us/library/ms633547(v=VS.85).aspx)
</dt> <dt>

[**ShowWindow**](https://msdn.microsoft.com/en-us/library/ms633548(v=VS.85).aspx)
</dt> <dt>

**Conceptual**
</dt> <dt>

[Windows](windows.md)
</dt> </dl>

 

 




