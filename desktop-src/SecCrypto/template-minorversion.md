---
Description: Retrieves the minor version number of the template.
ms.assetid: 3fc51d43-9113-4b4b-88ab-27cf6e5c4fa0
title: Template.MinorVersion property
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- Template.MinorVersion
api_type:
- COM
api_location:
- Capicom.dll
---

# Template.MinorVersion property

\[The **MinorVersion** property is available for use in the operating systems specified in the Requirements section. Instead, use the [**X509Extension Class**](https://msdn.microsoft.com/library/x5x51x86(v=VS.100).aspx) in the [**System.Security.Cryptography.X509Certificates**](https://msdn.microsoft.com/library/73091bzx(v=VS.71).aspx) namespace by calling the constructor that takes an OID as a parameter, and then use the OID for Certificate Template to retrieve the certificate extension template.\]

The **MinorVersion** property retrieves the minor version number of the template.

## Syntax


```VB
Template.MinorVersion As Long
```



## Property value

The minor version number of the template.

## Requirements



|                            |                                                                                        |
|----------------------------|----------------------------------------------------------------------------------------|
| Redistributable<br/> | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>             | <dl> <dt>Capicom.dll</dt> </dl> |



## See also

<dl> <dt>

[**Template**](template.md)
</dt> </dl>

 

 




