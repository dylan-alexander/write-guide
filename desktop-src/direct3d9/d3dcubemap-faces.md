---
Description: Defines the faces of a cubemap.
ms.assetid: 6d18b410-6f22-4202-86ae-6b3ef85e6f69
title: D3DCUBEMAP_FACES enumeration (D3D9Types.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- D3DCUBEMAP_FACES
api_type:
- HeaderDef
api_location:
- D3D9Types.h
---

# D3DCUBEMAP\_FACES enumeration

Defines the faces of a cubemap.

## Syntax


```C++
typedef enum D3DCUBEMAP_FACES { 
  D3DCUBEMAP_FACE_POSITIVE_X   = 0,
  D3DCUBEMAP_FACE_NEGATIVE_X   = 1,
  D3DCUBEMAP_FACE_POSITIVE_Y   = 2,
  D3DCUBEMAP_FACE_NEGATIVE_Y   = 3,
  D3DCUBEMAP_FACE_POSITIVE_Z   = 4,
  D3DCUBEMAP_FACE_NEGATIVE_Z   = 5,
  D3DCUBEMAP_FACE_FORCE_DWORD  = 0xffffffff
} D3DCUBEMAP_FACES, *LPD3DCUBEMAP_FACES;
```



## Constants

<dl> <dt>

<span id="D3DCUBEMAP_FACE_POSITIVE_X"></span><span id="d3dcubemap_face_positive_x"></span>**D3DCUBEMAP\_FACE\_POSITIVE\_X**
</dt> <dd>

Positive x-face of the cubemap.

</dd> <dt>

<span id="D3DCUBEMAP_FACE_NEGATIVE_X"></span><span id="d3dcubemap_face_negative_x"></span>**D3DCUBEMAP\_FACE\_NEGATIVE\_X**
</dt> <dd>

Negative x-face of the cubemap.

</dd> <dt>

<span id="D3DCUBEMAP_FACE_POSITIVE_Y"></span><span id="d3dcubemap_face_positive_y"></span>**D3DCUBEMAP\_FACE\_POSITIVE\_Y**
</dt> <dd>

Positive y-face of the cubemap.

</dd> <dt>

<span id="D3DCUBEMAP_FACE_NEGATIVE_Y"></span><span id="d3dcubemap_face_negative_y"></span>**D3DCUBEMAP\_FACE\_NEGATIVE\_Y**
</dt> <dd>

Negative y-face of the cubemap.

</dd> <dt>

<span id="D3DCUBEMAP_FACE_POSITIVE_Z"></span><span id="d3dcubemap_face_positive_z"></span>**D3DCUBEMAP\_FACE\_POSITIVE\_Z**
</dt> <dd>

Positive z-face of the cubemap.

</dd> <dt>

<span id="D3DCUBEMAP_FACE_NEGATIVE_Z"></span><span id="d3dcubemap_face_negative_z"></span>**D3DCUBEMAP\_FACE\_NEGATIVE\_Z**
</dt> <dd>

Negative z-face of the cubemap.

</dd> <dt>

<span id="D3DCUBEMAP_FACE_FORCE_DWORD"></span><span id="d3dcubemap_face_force_dword"></span>**D3DCUBEMAP\_FACE\_FORCE\_DWORD**
</dt> <dd>

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. This value is not used.

</dd> </dl>

## Requirements



|                   |                                                                                        |
|-------------------|----------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>D3D9Types.h</dt> </dl> |



## See also

<dl> <dt>

[Direct3D Enumerations](dx9-graphics-reference-d3d-enums.md)
</dt> <dt>

[**IDirect3DCubeTexture9::AddDirtyRect**](https://msdn.microsoft.com/library/Bb174330(v=VS.85).aspx)
</dt> <dt>

[**IDirect3DCubeTexture9::GetCubeMapSurface**](https://msdn.microsoft.com/library/Bb174331(v=VS.85).aspx)
</dt> <dt>

[**IDirect3DCubeTexture9::LockRect**](https://msdn.microsoft.com/library/Bb174334(v=VS.85).aspx)
</dt> <dt>

[**IDirect3DCubeTexture9::UnlockRect**](https://msdn.microsoft.com/library/Bb174335(v=VS.85).aspx)
</dt> </dl>

 

 




