---
Description: Adds a data object as a child of the ID3DXFileSaveData object.
ms.assetid: 710a1588-d766-4555-97a3-4b5a517ce805
title: ID3DXFileSaveObject::AddDataObject method (D3DX9Xof.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- ID3DXFileSaveObject.AddDataObject
api_type: 
- COM
api_location: 
- D3dx9.lib
- D3dx9.dll
---

# ID3DXFileSaveObject::AddDataObject method

Adds a data object as a child of the [**ID3DXFileSaveData**](id3dxfilesavedata.md) object.

## Syntax


```C++
HRESULT AddDataObject(
  [in]               REFGUID           rguidTemplate,
  [in]               LPCSTR            szName,
  [in]         const GUID              *pId,
  [in]               SIZE_T            cbSize,
  [in]               LPCVOID           pvData,
  [in, retval]       ID3DXFileSaveData **ppObj
);
```



## Parameters

<dl> <dt>

*rguidTemplate* \[in\]
</dt> <dd>

Type: **[REFGUID](https://go.microsoft.com/?linkid=9742306)**

GUID representing the data object's template.

</dd> <dt>

*szName* \[in\]
</dt> <dd>

Type: **[**LPCSTR**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

Pointer to the name of the data object. Specify **NULL** if the object does not have a name.

</dd> <dt>

*pId* \[in\]
</dt> <dd>

Type: **const [**GUID**](guid.md)\***

Pointer to a GUID representing the data object. Specify **NULL** if the object does not have a GUID.

</dd> <dt>

*cbSize* \[in\]
</dt> <dd>

Type: **[**SIZE\_T**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

Size of the data object, in bytes.

</dd> <dt>

*pvData* \[in\]
</dt> <dd>

Type: **[**LPCVOID**](https://msdn.microsoft.com/en-us/library/Aa383751(v=VS.85).aspx)**

Pointer to a buffer containing all required data in the data object.

</dd> <dt>

*ppObj* \[in, retval\]
</dt> <dd>

Type: **[**ID3DXFileSaveData**](id3dxfilesavedata.md)\*\***

Address of a pointer to an [**ID3DXFileSaveData**](id3dxfilesavedata.md) interface, representing the file data node to which the data object will be added.

</dd> </dl>

## Return value

Type: **[**HRESULT**](https://msdn.microsoft.com/en-us/library/Bb401631(v=MSDN.10).aspx)**

If the method succeeds, the return value is S\_OK. If the method fails, the return value can be one of the following: D3DXFERR\_BADOBJECT, DXFILEERR\_BADVALUE, E\_OUTOFMEMORY.

## Remarks

If a data reference object will reference the data object, either the szName or pId parameter must be non-**NULL**.

Save the created data to disk by using the [**ID3DXFileSaveObject::Save**](id3dxfilesaveobject--save.md) method.

## Requirements



|                    |                                                                                       |
|--------------------|---------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Xof.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>  |



## See also

<dl> <dt>

[ID3DXFileSaveObject](id3dxfilesaveobject.md)
</dt> </dl>

 

 




