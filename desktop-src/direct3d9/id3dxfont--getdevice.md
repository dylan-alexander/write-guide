---
Description: Retrieves the Direct3D device associated with the font object.
ms.assetid: c713cbe2-6e6e-476b-a995-14fa149cb088
title: ID3DXFont::GetDevice method (D3dx9core.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- ID3DXFont.GetDevice
api_type:
- COM
api_location:
- d3dx9.lib
- d3dx9.dll
---

# ID3DXFont::GetDevice method

Retrieves the Direct3D device associated with the font object.

## Syntax


```C++
HRESULT GetDevice(
  [out] LPDIRECT3DDEVICE9 *ppDevice
);
```



## Parameters

<dl> <dt>

*ppDevice* \[out\]
</dt> <dd>

Type: **[**LPDIRECT3DDEVICE9**](https://msdn.microsoft.com/library/Bb174336(v=VS.85).aspx)\***

Address of a pointer to an [**IDirect3DDevice9**](https://msdn.microsoft.com/library/Bb174336(v=VS.85).aspx) interface, representing the Direct3D device object associated with the font object.

</dd> </dl>

## Return value

Type: **[**HRESULT**](https://msdn.microsoft.com/en-us/library/Bb401631(v=MSDN.10).aspx)**

If the method succeeds, the return value is S\_OK. If the method fails, the return value can be one of the following: D3DERR\_INVALIDCALL, D3DXERR\_INVALIDDATA.

## Remarks

> [!Note]  
> Calling this method will increase the internal reference count on the [**IDirect3DDevice9**](https://msdn.microsoft.com/library/Bb174336(v=VS.85).aspx) interface. Be sure to call [**IUnknown**](https://msdn.microsoft.com/en-us/library/ms680509(v=VS.85).aspx) when you are done using this **IDirect3DDevice9** interface or you will have a memory leak.

 

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx9core.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[ID3DXFont](id3dxfont.md)
</dt> </dl>

 

 




