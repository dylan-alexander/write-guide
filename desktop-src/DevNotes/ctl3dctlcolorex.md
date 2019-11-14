---
Description: Handles the WM\_CTLCOLOR message for applications that use CTL3D.
ms.assetid: 8626a559-4856-4e7d-bf9c-edc48613b8f4
title: Ctl3dCtlColorEx function
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- Ctl3dCtlColorEx
api_type: 
- DllExport
api_location: 
- Ctl3d32.dll
---

# Ctl3dCtlColorEx function

Handles the **WM\_CTLCOLOR** message for applications that use CTL3D.

## Syntax


```C++
HBRUSH Ctl3dCtlColorEx(
   UINT   wm,
   WPARAM wParam,
   LPARAM lParam
);
```



## Parameters

<dl> <dt>

*wm* 
</dt> <dd>

The **WM\_CTLCOLOR** message for the application.

</dd> <dt>

*wParam* 
</dt> <dd>

A handle to the display context (DC).

</dd> <dt>

*lParam* 
</dt> <dd>

A handle to a child window (control).

</dd> </dl>

## Return value

Returns a handle to the appropriate brush if the function succeeds; otherwise, it returns `(HBRUSH)(0)` indicating that an error occurred.

## Remarks

This function has no associated import library or header file; you must call it using the [**LoadLibrary**](https://msdn.microsoft.com/en-us/library/ms684175(v=VS.85).aspx) and [**GetProcAddress**](https://msdn.microsoft.com/en-us/library/ms683212(v=VS.85).aspx) functions.

## Requirements



|                |                                                                                        |
|----------------|----------------------------------------------------------------------------------------|
| DLL<br/> | <dl> <dt>Ctl3d32.dll</dt> </dl> |



 

 




