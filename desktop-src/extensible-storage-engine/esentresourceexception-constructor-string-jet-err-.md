---
title: EsentResourceException constructor (String, JET_err)
TOCTitle: EsentResourceException constructor (String, JET_err)
ms:assetid: M:Microsoft.Isam.Esent.Interop.EsentResourceException.#ctor(System.String,Microsoft.Isam.Esent.Interop.JET_err)
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.isam.esent.interop.esentresourceexception.esentresourceexception(v=EXCHG.10)
ms:contentKeyID: 55107307
ms.date: 07/30/2014
ms.topic: reference
dev_langs:
- vb
- csharp
api_name: 
- Microsoft.Isam.Esent.Interop.EsentResourceException..ctor
topic_type: 
- kbSyntax
- apiref
api_type: 
- Managed
api_location: 
- Microsoft.Isam.Esent.Interop.dll
ROBOTS: INDEX,FOLLOW

---

# EsentResourceException constructor (String, JET_err)

Initializes a new instance of the EsentResourceException class.

**Namespace:**  [Microsoft.Isam.Esent.Interop](hh596136\(v=exchg.10\).md)  
**Assembly:**  Microsoft.Isam.Esent.Interop (in Microsoft.Isam.Esent.Interop.dll)

## Syntax

``` vb
'Declaration
Protected Sub New ( _
    description As String, _
    err As JET_err _
)
'Usage
Dim description As String
Dim err As JET_err

Dim instance As New EsentResourceException(description, _
    err)
```

``` csharp
protected EsentResourceException(
    string description,
    JET_err err
)
```

#### Parameters

  - description  
    Type: [System.String](https://docs.microsoft.com/dotnet/api/system.string?redirectedfrom=MSDN)  
    
    The description of the error.

<!-- end list -->

  - err  
    Type: [Microsoft.Isam.Esent.Interop.JET_err](hh564840\(v=exchg.10\).md)  
    
    The error code of the exception.

## See also

#### Reference

[EsentResourceException class](dn350557\(v=exchg.10\).md)

[EsentResourceException members](dn350580\(v=exchg.10\).md)

[EsentResourceException overload](dn350556\(v=exchg.10\).md)

[Microsoft.Isam.Esent.Interop namespace](hh596136\(v=exchg.10\).md)

