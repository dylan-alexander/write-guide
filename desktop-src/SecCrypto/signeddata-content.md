---
Description: Sets or retrieves the data to be signed. This is the default property.
ms.assetid: 554ca500-403d-4c2a-868e-9e635d0b358e
title: SignedData.Content property
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- SignedData.Content
api_type:
- COM
api_location:
- Capicom.dll
---

# SignedData.Content property

\[The **Content** property is available for use in the operating systems specified in the Requirements section. Instead, use the [**SignedCms Class**](https://msdn.microsoft.com/library/kz82bs5e(v=VS.90).aspx) in the [**System.Security.Cryptography.Pkcs**](https://msdn.microsoft.com/library/6see7k14(v=VS.100).aspx) namespace.\]

The **Content** property sets or retrieves the data to be signed. This is the default property.

## Syntax


```VB
SignedData.Content As String
```



## Property value

The data to be signed.

## Remarks

This property must be initialized before the [**Sign**](signeddata-sign.md) method is called. When the value of this property is reset, directly or indirectly, the whole [*state*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) of the object is reset, and any signature that was associated with the object before the property was changed is lost.

## Requirements



|                            |                                                                                        |
|----------------------------|----------------------------------------------------------------------------------------|
| Redistributable<br/> | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>             | <dl> <dt>Capicom.dll</dt> </dl> |



## See also

<dl> <dt>

[**SignedData**](signeddata.md)
</dt> </dl>

 

 




