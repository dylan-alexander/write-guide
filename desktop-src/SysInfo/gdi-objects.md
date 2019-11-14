---
Description: GDI objects support only one handle per object. Handles to GDI objects are private to a process. That is, only the process that created the GDI object can use the object handle.
ms.assetid: 699de25c-083d-4be3-a997-67418b7173e1
title: GDI Objects
ms.topic: article
ms.date: 05/31/2018
---

# GDI Objects

GDI objects support only one handle per object. Handles to GDI objects are private to a process. That is, only the process that created the GDI object can use the object handle.

There is a theoretical limit of 65,536 GDI handles per session. However, the maximum number of GDI handles that can be opened per session is usually lower, since it is affected by available memory.

**Windows 2000:** There is a limit of 16,384 GDI handles per session.

There is also a default per-process limit of GDI handles. To change this limit, set the following registry value:

**HKEY\_LOCAL\_MACHINE**\\**SOFTWARE**\\**Microsoft**\\**Windows NT**\\**CurrentVersion**\\**Windows**\\**GDIProcessHandleQuota**

This value can be set to a number between 256 and 65,536.

**Windows 2000:** This value can be set to a number between 256 and 16,384.

## Managing GDI Objects

The following table lists the GDI objects, along with each object's creator and destroyer functions. The creator functions either create the object and an object handle or simply return the existing object handle. The destroyer functions remove the object from memory, which invalidates the object handle.



| GDI object           | Creator function                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | Destroyer function                                           |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
| Bitmap               | [**CreateBitmap**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createbitmap), [**CreateBitmapIndirect**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createbitmapindirect), [**CreateCompatibleBitmap**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createcompatiblebitmap), [**CreateDIBitmap**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createdibitmap), [**CreateDIBSection**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createdibsection), [**CreateDiscardableBitmap**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-creatediscardablebitmap)                                                                                                                                                                                 | [**DeleteObject**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-deleteobject)                         |
| Brush                | [**CreateBrushIndirect**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createbrushindirect), [**CreateDIBPatternBrush**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createdibpatternbrush), [**CreateDIBPatternBrushPt**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createdibpatternbrushpt), [**CreateHatchBrush**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createhatchbrush), [**CreatePatternBrush**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createpatternbrush), [**CreateSolidBrush**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createsolidbrush)                                                                                                                                                                     | [**DeleteObject**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-deleteobject)                         |
| DC                   | [**CreateDC**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createdca)                                                                                                                                                                                                                                                                                                                                                                                                                                                             | [**DeleteDC**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-deletedc), [**ReleaseDC**](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-releasedc) |
| Enhanced metafile    | [**CreateEnhMetaFile**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createenhmetafilea)                                                                                                                                                                                                                                                                                                                                                                                                                                           | [**DeleteEnhMetaFile**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-deleteenhmetafile)               |
| Enhanced-metafile DC | [**CreateEnhMetaFile**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createenhmetafilea)                                                                                                                                                                                                                                                                                                                                                                                                                                           | [**CloseEnhMetaFile**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-closeenhmetafile)                 |
| Font                 | [**CreateFont**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createfonta), [**CreateFontIndirect**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createfontindirecta)                                                                                                                                                                                                                                                                                                                                                                                                       | [**DeleteObject**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-deleteobject)                         |
| Memory DC            | [**CreateCompatibleDC**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createcompatibledc)                                                                                                                                                                                                                                                                                                                                                                                                                                         | [**DeleteDC**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-deletedc)                                 |
| Metafile             | [**CreateMetaFile**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createmetafilea)                                                                                                                                                                                                                                                                                                                                                                                                                                                 | [**DeleteMetaFile**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-deletemetafile)                     |
| Metafile DC          | [**CreateMetaFile**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createmetafilea)                                                                                                                                                                                                                                                                                                                                                                                                                                                 | [**CloseMetaFile**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-closemetafile)                       |
| Palette              | [**CreatePalette**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createpalette)                                                                                                                                                                                                                                                                                                                                                                                                                                                   | [**DeleteObject**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-deleteobject)                         |
| Pen and extended pen | [**CreatePen**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createpen), [**CreatePenIndirect**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createpenindirect), [**ExtCreatePen**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-extcreatepen)                                                                                                                                                                                                                                                                                                                                                                     | [**DeleteObject**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-deleteobject)                         |
| Region               | [**CombineRgn**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-combinergn), [**CreateEllipticRgn**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createellipticrgn), [**CreateEllipticRgnIndirect**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createellipticrgnindirect), [**CreatePolygonRgn**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createpolygonrgn), [**CreatePolyPolygonRgn**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createpolypolygonrgn), [**CreateRectRgn**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createrectrgn), [**CreateRectRgnIndirect**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createrectrgnindirect), [**CreateRoundRectRgn**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-createroundrectrgn), [**ExtCreateRegion**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-extcreateregion), [**PathToRegion**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-pathtoregion) | [**DeleteObject**](https://docs.microsoft.com/windows/desktop/api/wingdi/nf-wingdi-deleteobject)                         |



 

 

 


