---
title: Render to a GDI Surface
description: Render to a GDI Surface
ms.assetid: a6096ff5-1e6e-4edb-b455-ea5d205072ff
ms.topic: article
ms.date: 05/31/2018
---

# Render to a GDI Surface

In some cases, you may want to be able to display [DirectWrite](direct-write-portal.md) text on a GDI surface. The [**IDWriteBitmapRenderTarget**](https://msdn.microsoft.com/en-us/library/Dd368165(v=VS.85).aspx) interface encapsulates a bitmap and device context to render text onto. You create an **IDWriteBitmapRenderTarget** by using the [**IDWriteGdiInterop::CreateBitmapRenderTarget**](https://msdn.microsoft.com/en-us/library/Dd371182(v=VS.85).aspx) method, as shown in the following code.


```C++
if (SUCCEEDED(hr))
{
    hr = g_pGdiInterop->CreateBitmapRenderTarget(hdc, r.right, r.bottom, &g_pBitmapRenderTarget);
}
```



To render with an [**IDWriteBitmapRenderTarget**](https://msdn.microsoft.com/en-us/library/Dd368165(v=VS.85).aspx), you must implement a custom text renderer callback interface derived from the [**IDWriteTextRenderer**](https://msdn.microsoft.com/en-us/library/Dd371523(v=VS.85).aspx) interface. You must implement methods for drawing a glyph run, underline, strikethrough, inline objects, and so on. For a complete list of the methods, see the [**IDWriteTextRenderer**](https://msdn.microsoft.com/en-us/library/Dd371523(v=VS.85).aspx) reference page. Not every method must be implemented, they can just return **E\_NOTIMPL**, and drawing will continue.

You can then draw the text by using the [**IDWriteTextLayout::Draw**](https://msdn.microsoft.com/en-us/library/Dd316726(v=VS.85).aspx) method and passing the callback interface that you implemented as a parameter. The **IDWriteTextLayout::Draw** method calls the methods of the custom renderer callback you provide. The [**DrawGlyphRun**](https://msdn.microsoft.com/en-us/library/Dd371526(v=VS.85).aspx), [**DrawUnderline**](https://msdn.microsoft.com/en-us/library/Dd371533(v=VS.85).aspx), [**DrawInlineObject**](https://msdn.microsoft.com/en-us/library/Dd371527(v=VS.85).aspx), and [**DrawStrikethrough**](https://msdn.microsoft.com/en-us/library/Dd371530(v=VS.85).aspx) methods perform the drawing functions.

In your implementation of [**DrawGlyphRun**](https://msdn.microsoft.com/en-us/library/Dd371526(v=VS.85).aspx), call the [**IDWriteBitmapRenderTarget::DrawGlyphRun**](https://msdn.microsoft.com/en-us/library/Dd368167(v=VS.85).aspx) method to draw the glyphs. The rendering of the underline, strikethrough and inline objects must be done by your custom renderer.

[**IDWriteBitmapRenderTarget::DrawGlyphRun**](https://msdn.microsoft.com/en-us/library/Dd368167(v=VS.85).aspx) has an optional RECT out parameter that contains the bounds of the area where the text was drawn. You can use this information to set the bounding rectangle for the device context with the [**SetBoundsRect**](/windows/win32/api/wingdi/nf-wingdi-setboundsrect) function that is provided by GDI. The following code is an example implementation of the [**DrawGlyphRun**](https://msdn.microsoft.com/en-us/library/Dd371526(v=VS.85).aspx) method of a custom renderer.


```C++
STDMETHODIMP GdiTextRenderer::DrawGlyphRun(
    __maybenull void* clientDrawingContext,
    FLOAT baselineOriginX,
    FLOAT baselineOriginY,
    DWRITE_MEASURING_MODE measuringMode,
    __in DWRITE_GLYPH_RUN const* glyphRun,
    __in DWRITE_GLYPH_RUN_DESCRIPTION const* glyphRunDescription,
    IUnknown* clientDrawingEffect
    )
{
    HRESULT hr = S_OK;

    // Pass on the drawing call to the render target to do the real work.
    RECT dirtyRect = {0};

    hr = pRenderTarget_->DrawGlyphRun(
        baselineOriginX,
        baselineOriginY,
        measuringMode,
        glyphRun,
        pRenderingParams_,
        RGB(0,200,255),
        &dirtyRect
        );
    

    return hr;
}
```



The [**IDWriteBitmapRenderTarget**](https://msdn.microsoft.com/en-us/library/Dd368165(v=VS.85).aspx) interface renders to a device context (DC) in memory. You get a handle to this DC by using the [**IDWriteBitmapRenderTarget::GetMemoryDC**](https://msdn.microsoft.com/en-us/library/Dd368171(v=VS.85).aspx) method. As soon as the drawing has been performed, the memory DC of the **IDWriteBitmapRenderTarget** object must be copied to the destination GDI surface.

You can retrieve the bounding rectangle by using the [**GetBoundsRect**](/windows/win32/api/wingdi/nf-wingdi-getboundsrect) function, then use the bounding rectangle with the [**BitBlt**](/windows/win32/api/wingdi/nf-wingdi-bitblt) function to copy the rendered [DirectWrite](direct-write-portal.md) text from the memory DC to the GDI surface as shown in the following code.


```C++
// Transfer from DWrite's rendering target to the window.
BitBlt(
    hdc,
    0, 0,
    size.cx, size.cy,
    memoryHdc,
    0, 0, 
    SRCCOPY | NOMIRRORBITMAP
    );
```



 

 




