---
title: D3DX11CreateAsyncTextureInfoProcessor function (D3DX11tex.h)
description: Note The D3DX (D3DX 9, D3DX 10, and D3DX 11) utility library is deprecated for Windows 8 and is not supported for Windows Store apps. See Remarks. Create a data processor to be used with a thread pump.
ms.assetid: 87de73a5-21f7-4abd-b83a-65c6761681c3
keywords:
- D3DX11CreateAsyncTextureInfoProcessor function Direct3D 11
topic_type:
- apiref
api_name:
- D3DX11CreateAsyncTextureInfoProcessor
api_location:
- D3DX11.lib
- D3DX11.dll
api_type:
- LibDef
ms.topic: reference
ms.date: 05/31/2018
---

# D3DX11CreateAsyncTextureInfoProcessor function

> [!Note]  
> The D3DX (D3DX 9, D3DX 10, and D3DX 11) utility library is deprecated for Windows 8 and is not supported for Windows Store apps. See Remarks.

 

Create a data processor to be used with a [**thread pump**](id3dx11threadpump.md).

## Syntax


```C++
HRESULT D3DX11CreateAsyncTextureInfoProcessor(
  _In_  D3DX11_IMAGE_INFO    *pImageInfo,
  _Out_ ID3DX11DataProcessor **ppDataProcessor
);
```



## Parameters

<dl> <dt>

*pImageInfo* \[in\]
</dt> <dd>

Type: **[**D3DX11\_IMAGE\_INFO**](d3dx11-image-info.md)\***

Optional. Identifies the characteristics of a texture (see [**D3DX11\_IMAGE\_INFO**](d3dx11-image-info.md)) when the data processor is created; set this to **NULL** to read the characteristics of a texture when the texture is loaded.

</dd> <dt>

*ppDataProcessor* \[out\]
</dt> <dd>

Type: **[**ID3DX11DataProcessor**](id3dx11dataprocessor.md)\*\***

Address of a pointer to a buffer that contains the data processor created (see [**ID3DX11DataProcessor Interface**](id3dx11dataprocessor.md)).

</dd> </dl>

## Return value

Type: **[**HRESULT**](https://msdn.microsoft.com/en-us/library/Bb401631(v=MSDN.10).aspx)**

The return value is one of the values listed in [Direct3D 11 Return Codes](d3d11-graphics-reference-returnvalues.md).

## Remarks

This API does creates a data-processor interface; [**D3DX11CreateAsyncTextureProcessor**](d3dx11createasynctextureprocessor.md) creates the data-processor interface and loads the texture.

There s no implementation of the  async loader  outside of D3DX 10, and D3DX 11.

For Windows Store apps, the DirectX samples (for example, the [Direct3D tutorial sample](https://go.microsoft.com/fwlink/p/?linkid=255263)) include the **BasicLoader** module that uses the Windows Runtime asynchronous programming model ([**AsyncBase**](https://msdn.microsoft.com/en-us/library/BR244878(v=VS.110).aspx)).

For Win32 desktop apps, you can use the [Concurrency Runtime](https://msdn.microsoft.com/en-us/library/Ee207192(v=VS.100).aspx) to implement something similar to the Windows Runtime asynchronous programming model.

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX11tex.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3DX11.lib</dt> </dl>  |



## See also

<dl> <dt>

[D3DX Functions](d3d11-graphics-reference-d3dx11-functions.md)
</dt> </dl>

 

 





