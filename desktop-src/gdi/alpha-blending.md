---
Description: Alpha blending is used to display an alpha bitmap, which is a bitmap that has transparent or semi-transparent pixels.
ms.assetid: 52a044cc-a471-4951-adbe-32319b8e3129
title: Alpha Blending (Windows GDI)
ms.topic: article
ms.date: 05/31/2018
---

# Alpha Blending

*Alpha blending* is used to display an alpha bitmap, which is a bitmap that has transparent or semi-transparent pixels. In addition to a red, green, and blue color channel, each pixel in an alpha bitmap has a transparency component known as its *alpha channel*. The alpha channel typically contains as many bits as a color channel. For example, an 8-bit alpha channel can represent 256 levels of transparency, from 0 (the entire bitmap is transparent) to 255 (the entire bitmap is opaque).

Alpha blending mechanisms are invoked by calling [**AlphaBlend**](/windows/desktop/api/WinGdi/nf-wingdi-alphablend), which references the [**BLENDFUNCTION**](/windows/desktop/api/Wingdi/ns-wingdi-blendfunction) structure.

Alpha values per pixel are only supported for 32-bpp BI\_RGB. This formula is defined as:


```C++
typedef struct {
  BYTE   Blue;
  BYTE   Green;
  BYTE   Red;
  BYTE   Alpha;
};
```



This is represented in memory as shown in the following table.



|       |       |       |       |
|-------|-------|-------|-------|
| 31:24 | 23:16 | 15:08 | 07:00 |
| Alpha | Red   | Green | Blue  |



 

Bitmaps may also be displayed with a transparency factor applied to the entire bitmap. Any bitmap format can be displayed with a global constant alpha value by setting **SourceConstantAlpha** in the [**BLENDFUNCTION**](/windows/desktop/api/Wingdi/ns-wingdi-blendfunction) structure. The global constant alpha value has 256 levels of transparency, from 0 (entire bitmap is completely transparent) to 255 (entire bitmap is completely opaque). The global constant alpha value is combined with the per-pixel alpha value.

For an example, see [Alpha Blending a Bitmap](alpha-blending-a-bitmap.md).

 

 



