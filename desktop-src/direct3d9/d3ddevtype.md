---
Description: Defines device types.
ms.assetid: 2bcdc476-7c42-4152-b107-58366faf2abd
title: D3DDEVTYPE enumeration (D3D9Types.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- D3DDEVTYPE
api_type:
- HeaderDef
api_location:
- D3D9Types.h
---

# D3DDEVTYPE enumeration

Defines device types.

## Syntax


```C++
typedef enum D3DDEVTYPE { 
  D3DDEVTYPE_HAL          = 1,
  D3DDEVTYPE_NULLREF      = 4,
  D3DDEVTYPE_REF          = 2,
  D3DDEVTYPE_SW           = 3,
  D3DDEVTYPE_FORCE_DWORD  = 0xffffffff
} D3DDEVTYPE, *LPD3DDEVTYPE;
```



## Constants

<dl> <dt>

<span id="D3DDEVTYPE_HAL"></span><span id="d3ddevtype_hal"></span>**D3DDEVTYPE\_HAL**
</dt> <dd>

Hardware rasterization. Shading is done with software, hardware, or mixed transform and lighting.

</dd> <dt>

<span id="D3DDEVTYPE_NULLREF"></span><span id="d3ddevtype_nullref"></span>**D3DDEVTYPE\_NULLREF**
</dt> <dd>

Initialize Direct3D on a computer that has neither hardware nor reference rasterization available, and enable resources for 3D content creation. See Remarks.

</dd> <dt>

<span id="D3DDEVTYPE_REF"></span><span id="d3ddevtype_ref"></span>**D3DDEVTYPE\_REF**
</dt> <dd>

Direct3D features are implemented in software; however, the reference rasterizer does make use of special CPU instructions whenever it can.

The reference device is installed by the Windows SDK 8.0 or later and is intended as an aid in debugging for development only.

</dd> <dt>

<span id="D3DDEVTYPE_SW"></span><span id="d3ddevtype_sw"></span>**D3DDEVTYPE\_SW**
</dt> <dd>

A pluggable software device that has been registered with [**IDirect3D9::RegisterSoftwareDevice**](https://msdn.microsoft.com/library/Bb174321(v=VS.85).aspx).

</dd> <dt>

<span id="D3DDEVTYPE_FORCE_DWORD"></span><span id="d3ddevtype_force_dword"></span>**D3DDEVTYPE\_FORCE\_DWORD**
</dt> <dd>

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. This value is not used.

</dd> </dl>

## Remarks

All methods of the [**IDirect3D9**](https://msdn.microsoft.com/library/Bb174300(v=VS.85).aspx) interface that take a **D3DDEVTYPE** device type will fail if D3DDEVTYPE\_NULLREF is specified. To use these methods, substitute D3DDEVTYPE\_REF in the method call.

A D3DDEVTYPE\_REF device should be created in D3DPOOL\_SCRATCH memory, unless vertex and index buffers are required. To support vertex and index buffers, create the device in D3DPOOL\_SYSTEMMEM memory.

If D3dref9.dll is installed, Direct3D will use the reference rasterizer to create a D3DDEVTYPE\_REF device type, even if D3DDEVTYPE\_NULLREF is specified. If D3dref9.dll is not available and D3DDEVTYPE\_NULLREF is specified, Direct3D will neither render nor present the scene.

## Requirements



|                   |                                                                                        |
|-------------------|----------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>D3D9Types.h</dt> </dl> |



## See also

<dl> <dt>

[Direct3D Enumerations](dx9-graphics-reference-d3d-enums.md)
</dt> <dt>

[**IDirect3D9::CheckDeviceFormat**](https://msdn.microsoft.com/library/Bb174309(v=VS.85).aspx)
</dt> <dt>

[**IDirect3D9::CheckDeviceMultiSampleType**](https://msdn.microsoft.com/library/Bb174311(v=VS.85).aspx)
</dt> <dt>

[**IDirect3D9::CheckDeviceType**](https://msdn.microsoft.com/library/Bb174312(v=VS.85).aspx)
</dt> <dt>

[**IDirect3D9::CreateDevice**](https://msdn.microsoft.com/library/Bb174313(v=VS.85).aspx)
</dt> <dt>

[**IDirect3D9::GetDeviceCaps**](https://msdn.microsoft.com/library/Bb174320(v=VS.85).aspx)
</dt> <dt>

[**D3DDEVICE\_CREATION\_PARAMETERS**](d3ddevice-creation-parameters.md)
</dt> </dl>

 

 




