---
Description: A helper structure containing member type information.
ms.assetid: 5580122d-c700-4632-8fcf-903519f2429e
title: D3DXSHADER_TYPEINFO structure (D3dx9shader.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- D3DXSHADER_TYPEINFO
api_type: 
- HeaderDef
api_location: 
- d3dx9shader.h
---

# D3DXSHADER\_TYPEINFO structure

A helper structure containing member type information.

## Syntax


```C++
typedef struct D3DXSHADER_TYPEINFO {
  WORD  Class;
  WORD  Type;
  WORD  Rows;
  WORD  Columns;
  WORD  Elements;
  WORD  StructMembers;
  DWORD StructMemberInfo;
} D3DXSHADER_TYPEINFO, *LPD3DXSHADER_TYPEINFO;
```



## Members

<dl> <dt>

**Class**
</dt> <dd>

Type: **[**WORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

</dd> <dd>

Shader object type. See [**D3DXPARAMETER\_CLASS**](https://msdn.microsoft.com/en-us/library/Bb205378(v=VS.85).aspx).

</dd> <dt>

**Type**
</dt> <dd>

Type: **[**WORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

</dd> <dd>

Data type. See [**D3DXPARAMETER\_TYPE**](https://msdn.microsoft.com/en-us/library/Bb205380(v=VS.85).aspx).

</dd> <dt>

**Rows**
</dt> <dd>

Type: **[**WORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

</dd> <dd>

Number of matrix rows (matrices).

</dd> <dt>

**Columns**
</dt> <dd>

Type: **[**WORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

</dd> <dd>

Number of columns (vectors and matrices).

</dd> <dt>

**Elements**
</dt> <dd>

Type: **[**WORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

</dd> <dd>

Array dimension.

</dd> <dt>

**StructMembers**
</dt> <dd>

Type: **[**WORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

</dd> <dd>

Number of structure members.

</dd> <dt>

**StructMemberInfo**
</dt> <dd>

Type: **[**DWORD**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

</dd> <dd>

Array of structure member information, D3DXSHADER\_STRUCTMEMBERINFO\[*StructMembers*\]. See [**D3DXSHADER\_STRUCTMEMBERINFO**](d3dxshader-structmemberinfo.md).

</dd> </dl>

## Remarks

The type information is part of [**D3DXSHADER\_STRUCTMEMBERINFO**](d3dxshader-structmemberinfo.md).

## Requirements



|                   |                                                                                          |
|-------------------|------------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>D3dx9shader.h</dt> </dl> |



## See also

<dl> <dt>

[D3DX Structures](dx9-graphics-reference-d3dx-structures.md)
</dt> <dt>

[**D3DXSHADER\_CONSTANTINFO**](d3dxshader-constantinfo.md)
</dt> </dl>

 

 




