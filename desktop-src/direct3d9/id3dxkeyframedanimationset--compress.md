---
Description: Transforms animations in an animation set into a compressed format and returns a pointer to the buffer that stores the compressed data.
ms.assetid: b70b6dfb-545f-4309-ab72-9543c3c48fc4
title: ID3DXKeyframedAnimationSet::Compress method (D3dx9anim.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- ID3DXKeyframedAnimationSet.Compress
api_type: 
- COM
api_location: 
- d3dx9.lib
- d3dx9.dll
---

# ID3DXKeyframedAnimationSet::Compress method

Transforms animations in an animation set into a compressed format and returns a pointer to the buffer that stores the compressed data.

## Syntax


```C++
HRESULT Compress(
  [in]  DWORD        Flags,
  [in]  FLOAT        Lossiness,
  [in]  LPD3DXFRAME  pHierarchy,
  [out] LPD3DXBUFFER *ppCompressedData
);
```



## Parameters

<dl> <dt>

*Flags* \[in\]
</dt> <dd>

Type: **[**DWORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

One of the [**D3DXCOMPRESSION\_FLAGS**](https://msdn.microsoft.com/en-us/library/Bb172734(v=VS.85).aspx) values that define the compression mode used for storing compressed animation set data. D3DXCOMPRESS\_DEFAULT is the only value currently supported.

</dd> <dt>

*Lossiness* \[in\]
</dt> <dd>

Type: **[**FLOAT**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

Desired compression loss ratio, in the range from 0 to 1.

</dd> <dt>

*pHierarchy* \[in\]
</dt> <dd>

Type: **[**LPD3DXFRAME**](d3dxframe.md)**

Pointer to a [**D3DXFRAME**](d3dxframe.md) transformation frame hierarchy. Can be **NULL**.

</dd> <dt>

*ppCompressedData* \[out\]
</dt> <dd>

Type: **[**LPD3DXBUFFER**](id3dxbuffer.md)\***

Address of a pointer to the [**ID3DXBuffer**](id3dxbuffer.md) compressed animation set.

</dd> </dl>

## Return value

Type: **[**HRESULT**](https://msdn.microsoft.com/en-us/library/Bb401631(v=MSDN.10).aspx)**

If the method succeeds, the return value is S\_OK. If the method fails, the return value can be one of the following values: D3DERR\_INVALIDCALL, E\_OUTOFMEMORY.

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx9anim.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[ID3DXKeyframedAnimationSet](id3dxkeyframedanimationset.md)
</dt> </dl>

 

 




