---
Description: Returns the normalized version of a 2D vector.
ms.assetid: fac4f269-2778-4500-af9e-23a0112543b0
title: D3DXVec2Normalize function (D3DX10Math.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- D3DXVec2Normalize
api_type: 
- LibDef
api_location: 
- D3DX10.lib
- D3DX10.dll
---

# D3DXVec2Normalize function

Returns the normalized version of a 2D vector.

## Syntax


```C++
D3DXVECTOR2* D3DXVec2Normalize(
  _Inout_       D3DXVECTOR2 *pOut,
  _In_    const D3DXVECTOR2 *pV
);
```



## Parameters

<dl> <dt>

*pOut* \[in, out\]
</dt> <dd>

Type: **[**D3DXVECTOR2**](https://msdn.microsoft.com/en-us/library/Bb205544(v=VS.85).aspx)\***

Pointer to the [**D3DXVECTOR2**](d3d10-d3dxvector2.md) that is the result of the operation.

</dd> <dt>

*pV* \[in\]
</dt> <dd>

Type: **const [**D3DXVECTOR2**](https://msdn.microsoft.com/en-us/library/Bb205544(v=VS.85).aspx)\***

Pointer to the source D3DXVECTOR2 structure.

</dd> </dl>

## Return value

Type: **[**D3DXVECTOR2**](https://msdn.microsoft.com/en-us/library/Bb205544(v=VS.85).aspx)\***

Pointer to a D3DXVECTOR2 structure that is the normalized version of the vector.

## Remarks

The return value for this function is the same value returned in the pOut parameter. In this way, the D3DXVec2Normalize function can be used as a parameter for another function.

## Requirements



|                    |                                                                                         |
|--------------------|-----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX10Math.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3DX10.lib</dt> </dl>   |



## See also

<dl> <dt>

[Math Functions](d3d10-graphics-reference-d3dx10-functions-math.md)
</dt> </dl>

 

 




