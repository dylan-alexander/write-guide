---
title: IDWriteFactory2 interface
description: The root factory interface for all DirectWrite objects.
ms.assetid: 1D3EEC28-EAB3-4FA2-98E9-7A8FDAF6E6FE
keywords:
- IDWriteFactory1 interface Direct Write
- IDWriteFactory1 interface Direct Write , described
topic_type:
- apiref
api_name:
- IDWriteFactory1
api_location:
- dwrite.dll
api_type:
- COM
ms.topic: reference
ms.date: 05/31/2018
---

# IDWriteFactory2 interface

The root factory interface for all [DirectWrite](direct-write-portal.md) objects.

## Members

The **IDWriteFactory1** interface inherits from [**IDWriteFactory1**](https://msdn.microsoft.com/en-us/library/Hh780401(v=VS.85).aspx). **IDWriteFactory2** also has these types of members:

-   [Methods](#methods)

### Methods

The **IDWriteFactory1** interface has these methods.



| Method                                                                             | Description                                                                                                |
|:-----------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------|
| [**CreateCustomRenderingParams**](idwritefactory2-createcustomrenderingparams.md) | Creates a rendering parameters object with the specified properties.<br/>                            |
| [**CreateFontFallbackBuilder**](https://msdn.microsoft.com/en-us/library/Dn280449(v=VS.85).aspx)     | Creates a font fallback builder object.<br/>                                                         |
| [**CreateGlyphRunAnalysis**](idwritefactory2-createglyphrunanalysis.md)           | Creates a glyph run analysis object, which encapsulates information used to render a glyph run.<br/> |
| [**GetSystemFontFallback**](idwritefactory2-getsystemfontfallback.md)             | Creates a font fallback object from the system font fallback list.<br/>                              |
| [**TranslateColorGlyphRun**](https://msdn.microsoft.com/en-us/library/Dn280451(v=VS.85).aspx)           | This method is called on a glyph run to translate it in to multiple color glyph runs.<br/>           |



 

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8.1 \[desktop apps \| UWP apps\]<br/>                                     |
| Minimum supported server<br/> | Windows Server 2012 R2 \[desktop apps \| UWP apps\]<br/>                          |
| Minimum supported phone<br/>  | Windows Phone 8.1 \[Windows Phone Silverlight 8.1 and Windows Runtime apps\]<br/> |
| Library<br/>                  | <dl> <dt>Dwrite.lib</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>Dwrite.dll</dt> </dl>   |



## See also

<dl> <dt>

[**IDWriteFactory1**](https://msdn.microsoft.com/en-us/library/Hh780401(v=VS.85).aspx)
</dt> <dt>

[**IDWriteFactory**](https://msdn.microsoft.com/en-us/library/Dd368183(v=VS.85).aspx)
</dt> </dl>

 

 





