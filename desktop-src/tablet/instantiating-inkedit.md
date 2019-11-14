---
Description: This topic describes the various ways that you can instantiate an InkEdit control.
ms.assetid: 3ab0f10e-1a0d-4d0b-b5b2-69dc96570b33
title: Instantiating InkEdit
ms.topic: article
ms.date: 05/31/2018
---

# Instantiating InkEdit

This topic describes the various ways that you can instantiate an [InkEdit](inkedit-control.md) control.

## Visual Basic .NET and C\#

If you are working with Microsoft Visual Basic .NET or C\#, drag the [InkEdit](https://msdn.microsoft.com/library/ms701682(v=VS.85).aspx) control from the Toolbox in Visual Studio to the form or page where you want the control to appear.

## Win32/C++

The [InkEdit](inkedit-control-reference.md) control is a superclass of the Rich Edit 4.5 Win32 OLE embeddable control.

Win32 applications instantiate the [InkEdit](inkedit-control-reference.md) control by calling [CreateWindow()](https://msdn.microsoft.com/library/ms632679(v=VS.85).aspx) and passing INKEDIT as the window class. INKEDIT is defined in InkEd.h. After the control is created, you can "talk" to the control with messages. Rich Edit messages (EM\_\*) are passed from InkEdit to Rich Edit unaltered; all of the existing Rich Edit functionality is available.

To create an [InkEdit](inkedit-control-reference.md) control, call the [CreateWindow()](https://msdn.microsoft.com/library/ms632679(v=VS.85).aspx) function, specifying the InkEdit window class. Use [LoadLibrary()](https://msdn.microsoft.com/en-us/library/ms684175(v=VS.85).aspx) to register InkEd.dll. Specify the INKEDIT\_CLASS defined constant for the window class parameter and use the window styles as specified in the following examples.

### Instantiating a Multiline InkEdit Control


```C++
//...
HMODULE s_hlib;    
s_hlib= LoadLibrary("InkEd.dll");
//...
m_hwndInkEdit = CreateWindowW(INKEDIT_CLASS, NULL,
WS_CHILD|WS_VISIBLE|WS_BORDER|ES_MULTILINE,
rt.left, rt.top, rt.right, rt.bottom,
m_hWnd, NULL, hInst, NULL);
```



### Instantiating a Single-Line InkEdit Control


```C++
//...
HMODULE s_hlib;    
s_hlib= LoadLibrary("InkEd.dll");
//...
m_hwndInkEdit = CreateWindowW(INKEDIT_CLASS, NULL,
WS_CHILD|WS_VISIBLE|WS_BORDER,
rt.left, rt.top, rt.right, rt.bottom,
m_hWnd, NULL, hInst, NULL);
```



> [!Note]  
> Unlike with RichEdit, you must be sure to call [CoInitialize()](https://msdn.microsoft.com/en-us/library/ms678543(v=VS.85).aspx) before creating the [InkEdit](inkedit-control-reference.md) control. Call [CoUninitialize()](https://msdn.microsoft.com/en-us/library/ms688715(v=VS.85).aspx) when your application shuts down. After calling CoUninitialize(), you must call [FreeLibrary(s\_hlib)](https://msdn.microsoft.com/en-us/library/ms683152(v=VS.85).aspx) to decrement the reference count on the InkEdit.dll file.

 

If you use the [ES\_NOIME](https://msdn.microsoft.com/library/Bb774367(v=VS.85).aspx) window style, the built-in correction support is not available. If you don't specify a parent window, the control is created as a top-level window and the WS\_SYSMENU style is added; this also disables the built-in correction support.

## Related topics

<dl> <dt>

[Adding Ink Controls to a Project](adding-ink-controls-to-a-project.md)
</dt> </dl>

 

 



