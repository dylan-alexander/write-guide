---
title: JET_LOGTIME.Inequality operator 
TOCTitle: 'Inequality operator '
ms:assetid: M:Microsoft.Isam.Esent.Interop.JET_LOGTIME.op_Inequality(Microsoft.Isam.Esent.Interop.JET_LOGTIME,Microsoft.Isam.Esent.Interop.JET_LOGTIME)
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.isam.esent.interop.jet_logtime.op_inequality(v=EXCHG.10)
ms:contentKeyID: 39511232
ms.date: 07/30/2014
ms.topic: reference
f1_keywords:
- Microsoft.Isam.Esent.Interop.JET_LOGTIME.Inequality
dev_langs:
- CSharp
- JScript
- VB
- other
api_name: 
- Microsoft.Isam.Esent.Interop.JET_LOGTIME.Inequality
- Microsoft.Isam.Esent.Interop.JET_LOGTIME.op_Inequality
topic_type: 
- apiref
- kbSyntax
api_type: 
- Managed
api_location: 
- Microsoft.Isam.Esent.Interop.dll
ROBOTS: INDEX,FOLLOW

---

# JET_LOGTIME.Inequality operator

Determines whether two specified instances of JET_LOGTIME are not equal.

**Namespace:**  [Microsoft.Isam.Esent.Interop](hh596136\(v=exchg.10\).md)  
**Assembly:**  Microsoft.Isam.Esent.Interop (in Microsoft.Isam.Esent.Interop.dll)

## Syntax

``` vb
'Declaration
Public Shared Operator <> ( _
    lhs As JET_LOGTIME, _
    rhs As JET_LOGTIME _
) As Boolean
'Usage
Dim lhs As JET_LOGTIME
Dim rhs As JET_LOGTIME
Dim returnValue As Boolean

returnValue = (lhs <> rhs)
```

``` csharp
public static bool operator !=(
    JET_LOGTIME lhs,
    JET_LOGTIME rhs
)
```

#### Parameters

  - lhs  
    Type: [Microsoft.Isam.Esent.Interop.JET_LOGTIME](hh557188\(v=exchg.10\).md)  
    
    The first instance to compare.

<!-- end list -->

  - rhs  
    Type: [Microsoft.Isam.Esent.Interop.JET_LOGTIME](hh557188\(v=exchg.10\).md)  
    
    The second instance to compare.

#### Return value

Type: [System.Boolean](https://docs.microsoft.com/dotnet/api/system.boolean?redirectedfrom=MSDN)  
True if the two instances are not equal.  

## See also

#### Reference

[JET_LOGTIME structure](hh557188\(v=exchg.10\).md)

[JET_LOGTIME members](hh579151\(v=exchg.10\).md)

[Microsoft.Isam.Esent.Interop namespace](hh596136\(v=exchg.10\).md)

