---
Description: Sets or retrieves the Certificate object that represents the certificate of a signer of the data.
ms.assetid: 92ac209e-59b5-4a75-922d-d61629ca41b1
title: Signer.Certificate property
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- Signer.Certificate
api_type:
- COM
api_location:
- Capicom.dll
---

# Signer.Certificate property

\[The **Certificate** property is available for use in the operating systems specified in the Requirements section. Instead, use the [**CmsSigner Class**](https://msdn.microsoft.com/library/5x3db70t(v=VS.90).aspx) in the [**System.Security.Cryptography.Pkcs**](https://msdn.microsoft.com/library/6see7k14(v=VS.100).aspx) namespace.\]

The **Certificate** property sets or retrieves the [**Certificate**](certificate.md) object that represents the certificate of a signer of the data. This is the default property.

## Syntax


```VB
Signer.Certificate As Certificate
```



## Property value

The [**Certificate**](certificate.md) object that represents the certificate of a signer of the data.

## Remarks

When the value of this property is reset, directly or indirectly, the whole [*state*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) of the object is reset.

## Requirements



|                            |                                                                                        |
|----------------------------|----------------------------------------------------------------------------------------|
| Redistributable<br/> | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>             | <dl> <dt>Capicom.dll</dt> </dl> |



## See also

<dl> <dt>

[**Signer**](signer.md)
</dt> </dl>

 

 




