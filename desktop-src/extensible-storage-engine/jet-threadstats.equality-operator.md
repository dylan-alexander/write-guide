---
title: JET_THREADSTATS.Equality operator  (Microsoft.Isam.Esent.Interop.Vista)
TOCTitle: 'Equality operator '
ms:assetid: M:Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS.op_Equality(Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS,Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS)
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.isam.esent.interop.vista.jet_threadstats.op_equality(v=EXCHG.10)
ms:contentKeyID: 39515069
ms.date: 07/30/2014
ms.topic: reference
f1_keywords:
- Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS.Equality
dev_langs:
- CSharp
- JScript
- VB
- other
api_name: 
- Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS.Equality
- Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS.op_Equality
topic_type: 
- kbSyntax
- apiref
api_type: 
- Managed
api_location: 
- Microsoft.Isam.Esent.Interop.dll
ROBOTS: INDEX,FOLLOW

---

# JET_THREADSTATS.Equality operator

Determines whether two specified instances of JET_THREADSTATS are equal.

**Namespace:**  [Microsoft.Isam.Esent.Interop.Vista](hh558039\(v=exchg.10\).md)  
**Assembly:**  Microsoft.Isam.Esent.Interop (in Microsoft.Isam.Esent.Interop.dll)

## Syntax

``` vb
'Declaration
Public Shared Operator = ( _
    lhs As JET_THREADSTATS, _
    rhs As JET_THREADSTATS _
) As Boolean
'Usage
Dim lhs As JET_THREADSTATS
Dim rhs As JET_THREADSTATS
Dim returnValue As Boolean

returnValue = (lhs = rhs)
```

``` csharp
public static bool operator ==(
    JET_THREADSTATS lhs,
    JET_THREADSTATS rhs
)
```

#### Parameters

  - lhs  
    Type: [Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS](hh578565\(v=exchg.10\).md)  
    
    The first instance to compare.

<!-- end list -->

  - rhs  
    Type: [Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS](hh578565\(v=exchg.10\).md)  
    
    The second instance to compare.

#### Return value

Type: [System.Boolean](https://docs.microsoft.com/dotnet/api/system.boolean?redirectedfrom=MSDN)  
True if the two instances are equal.  

## See also

#### Reference

[JET_THREADSTATS structure](hh578565\(v=exchg.10\).md)

[JET_THREADSTATS members](hh579250\(v=exchg.10\).md)

[Microsoft.Isam.Esent.Interop.Vista namespace](hh558039\(v=exchg.10\).md)

