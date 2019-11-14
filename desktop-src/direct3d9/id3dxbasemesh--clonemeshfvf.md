---
Description: Clones a mesh using a flexible vertex format (FVF) code.
ms.assetid: b7d23ea9-1a2f-46e3-bcb5-82040d2a1e12
title: ID3DXBaseMesh::CloneMeshFVF method (D3DX9Mesh.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- ID3DXBaseMesh.CloneMeshFVF
api_type:
- COM
api_location:
- d3dx9.lib
- d3dx9.dll
---

# ID3DXBaseMesh::CloneMeshFVF method

Clones a mesh using a flexible vertex format (FVF) code.

## Syntax


```C++
HRESULT CloneMeshFVF(
  [in]          DWORD             Options,
  [in]          DWORD             FVF,
  [in]          LPDIRECT3DDEVICE9 pDevice,
  [out, retval] LPD3DXMESH        *ppCloneMesh
);
```



## Parameters

<dl> <dt>

*Options* \[in\]
</dt> <dd>

Type: **[**DWORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

A combination of one or more [**D3DXMESH**](https://msdn.microsoft.com/en-us/library/Bb205370(v=VS.85).aspx) flags specifying creation options for the mesh.

</dd> <dt>

*FVF* \[in\]
</dt> <dd>

Type: **[**DWORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

Combination of FVF codes, which specifies the vertex format for the vertices in the output mesh. For the values of the codes, see [D3DFVF](d3dfvf.md).

</dd> <dt>

*pDevice* \[in\]
</dt> <dd>

Type: **[**LPDIRECT3DDEVICE9**](https://msdn.microsoft.com/library/Bb174336(v=VS.85).aspx)**

Pointer to an [**IDirect3DDevice9**](https://msdn.microsoft.com/library/Bb174336(v=VS.85).aspx) interface representing the device object associated with the mesh.

</dd> <dt>

*ppCloneMesh* \[out, retval\]
</dt> <dd>

Type: **[**LPD3DXMESH**](id3dxmesh.md)\***

Address of a pointer to an [**ID3DXMesh**](id3dxmesh.md) interface, representing the cloned mesh.

</dd> </dl>

## Return value

Type: **[**HRESULT**](https://msdn.microsoft.com/en-us/library/Bb401631(v=MSDN.10).aspx)**

If the method succeeds, the return value is D3D\_OK. If the method fails, the return value can be one of the following: D3DERR\_INVALIDCALL, E\_OUTOFMEMORY.

## Remarks

**ID3DXBaseMesh::CloneMeshFVF** is used to reformat and change the vertex data layout. This is done by creating a new mesh object. For example, use it to to add space for normals, texture coordinates, colors, weights, etc. that were not present before.

[**ID3DXBaseMesh::UpdateSemantics**](id3dxbasemesh--updatesemantics.md) updates the vertex declaration with different semantic information without changing the layout of the vertex buffer. This method does not modify the contents of the vertex buffer. For example, use it to relabel a 3D texture coordinate as a binormal or tangent or vice versa.

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Mesh.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[ID3DXBaseMesh](id3dxbasemesh.md)
</dt> <dt>

[**D3DXFVFFromDeclarator**](d3dxfvffromdeclarator.md)
</dt> </dl>

 

 




