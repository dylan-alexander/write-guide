---
Description: Determines the product of the given matrix and the current matrix.
ms.assetid: 4d374a7b-99e0-4313-970d-b0e7cf3e97ce
title: ID3DXMATRIXStack::MultMatrixLocal method (D3DX10.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- ID3DXMATRIXStack.MultMatrixLocal
api_type: 
- COM
api_location: 
- D3DX10.lib
- D3DX10.dll
---

# ID3DXMATRIXStack::MultMatrixLocal method

Determines the product of the given matrix and the current matrix.

## Syntax


```C++
HRESULT MultMatrixLocal(
  [in] const D3DXMATRIX *pM
);
```



## Parameters

<dl> <dt>

*pM* \[in\]
</dt> <dd>

Type: **const [**D3DXMATRIX**](https://msdn.microsoft.com/en-us/library/Bb172912(v=VS.85).aspx)\***

Pointer to the D3DXMATRIX structure to be multiplied with the current matrix.

</dd> </dl>

## Return value

Type: **[**HRESULT**](https://msdn.microsoft.com/en-us/library/Bb401631(v=MSDN.10).aspx)**

If the method succeeds, the return value is D3D\_OK. If the method fails, the return value can be D3DERR\_INVALIDCALL.

## Remarks

This method left-multiplies the given matrix to the current matrix (transformation is about the local origin of the object).


```
m_pstack[m_currentPos] = (*pMat) * m_pstack[m_currentPos];
```



This method does not add an item to the stack, it replaces the current matrix with the product of the given matrix and the current matrix.

## Requirements



|                    |                                                                                       |
|--------------------|---------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX10.h</dt> </dl>   |
| Library<br/> | <dl> <dt>D3DX10.lib</dt> </dl> |



## See also

<dl> <dt>

[ID3DXMatrixStack](d3d10-id3dxmatrixstack.md)
</dt> <dt>

[D3DX Interfaces](d3d10-graphics-reference-d3dx10-interfaces.md)
</dt> </dl>

 

 




