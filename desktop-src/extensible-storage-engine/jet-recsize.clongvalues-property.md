---
title: JET_RECSIZE.cLongValues property  (Microsoft.Isam.Esent.Interop.Vista)
TOCTitle: 'cLongValues property '
ms:assetid: P:Microsoft.Isam.Esent.Interop.Vista.JET_RECSIZE.cLongValues
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.isam.esent.interop.vista.jet_recsize.clongvalues(v=EXCHG.10)
ms:contentKeyID: 39515366
ms.date: 07/30/2014
ms.topic: reference
f1_keywords:
- Microsoft.Isam.Esent.Interop.Vista.JET_RECSIZE.cLongValues
dev_langs:
- CSharp
- JScript
- VB
- other
api_name: 
- Microsoft.Isam.Esent.Interop.Vista.JET_RECSIZE.get_cLongValues
- Microsoft.Isam.Esent.Interop.Vista.JET_RECSIZE.set_cLongValues
- Microsoft.Isam.Esent.Interop.Vista.JET_RECSIZE.cLongValues
topic_type: 
- apiref
- kbSyntax
api_type: 
- Managed
api_location: 
- Microsoft.Isam.Esent.Interop.dll
ROBOTS: INDEX,FOLLOW

---

# JET_RECSIZE.cLongValues property

Gets the total number of long values stored in the long-value tree for this record. This does not include intrinsic long values.

**Namespace:**  [Microsoft.Isam.Esent.Interop.Vista](hh558039\(v=exchg.10\).md)  
**Assembly:**  Microsoft.Isam.Esent.Interop (in Microsoft.Isam.Esent.Interop.dll)

## Syntax

``` vb
'Declaration
Public Property cLongValues As Long
    Get
    Friend Set
'Usage
Dim instance As JET_RECSIZE
Dim value As Long

value = instance.cLongValues
```

``` csharp
public long cLongValues { get; internal set; }
```

#### Property value

Type: [System.Int64](https://docs.microsoft.com/dotnet/api/system.int64?redirectedfrom=MSDN)  

## See also

#### Reference

[JET_RECSIZE structure](hh557010\(v=exchg.10\).md)

[JET_RECSIZE members](hh557127\(v=exchg.10\).md)

[Microsoft.Isam.Esent.Interop.Vista namespace](hh558039\(v=exchg.10\).md)

