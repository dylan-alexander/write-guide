---
Description: Retrieves the content of the user notice.
ms.assetid: dcf73357-253d-4160-be4e-f826296f5eaa
title: Qualifier.ExplicitText property
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- Qualifier.ExplicitText
api_type:
- COM
api_location:
- Capicom.dll
---

# Qualifier.ExplicitText property

\[The **ExplicitText** property is available for use in the operating systems specified in the Requirements section. Instead, use the [**X509Extension Class**](https://msdn.microsoft.com/library/x5x51x86(v=VS.100).aspx) in the [**System.Security.Cryptography.X509Certificates**](https://msdn.microsoft.com/library/73091bzx(v=VS.71).aspx) namespace by calling the constructor that takes an OID as a parameter, and then use the OID for Certificate Policies to process qualifiers that are part of the policy information in the Certificate Policies extension.\]

The **ExplicitText** property retrieves the content of the user notice. This property may be empty.

## Syntax


```VB
Qualifier.ExplicitText As String
```



## Property value

The content of the user notice.

## Requirements



|                            |                                                                                        |
|----------------------------|----------------------------------------------------------------------------------------|
| Redistributable<br/> | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>             | <dl> <dt>Capicom.dll</dt> </dl> |



## See also

<dl> <dt>

[**Qualifier**](qualifier.md)
</dt> </dl>

 

 




