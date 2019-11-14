---
title: JET_THREADSTATS.Add method  (Microsoft.Isam.Esent.Interop.Vista)
TOCTitle: 'Add method '
ms:assetid: M:Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS.Add(Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS,Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS)
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.isam.esent.interop.vista.jet_threadstats.add(v=EXCHG.10)
ms:contentKeyID: 39514259
ms.date: 07/30/2014
ms.topic: reference
f1_keywords:
- Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS.Add
dev_langs:
- CSharp
- JScript
- VB
- other
api_name: 
- Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS.Add
topic_type: 
- kbSyntax
- apiref
api_type: 
- Managed
api_location: 
- Microsoft.Isam.Esent.Interop.dll
ROBOTS: INDEX,FOLLOW

---

# JET_THREADSTATS.Add method

Add the stats in two JET_THREADSTATS structures.

**Namespace:**  [Microsoft.Isam.Esent.Interop.Vista](hh558039\(v=exchg.10\).md)  
**Assembly:**  Microsoft.Isam.Esent.Interop (in Microsoft.Isam.Esent.Interop.dll)

## Syntax

``` vb
'Declaration
Public Shared Function Add ( _
    t1 As JET_THREADSTATS, _
    t2 As JET_THREADSTATS _
) As JET_THREADSTATS
'Usage
Dim t1 As JET_THREADSTATS
Dim t2 As JET_THREADSTATS
Dim returnValue As JET_THREADSTATS

returnValue = JET_THREADSTATS.Add(t1, t2)
```

``` csharp
public static JET_THREADSTATS Add(
    JET_THREADSTATS t1,
    JET_THREADSTATS t2
)
```

#### Parameters

  - t1  
    Type: [Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS](hh578565\(v=exchg.10\).md)  
    
    The first JET_THREADSTATS.

<!-- end list -->

  - t2  
    Type: [Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS](hh578565\(v=exchg.10\).md)  
    
    The second JET_THREADSTATS.

#### Return value

Type: [Microsoft.Isam.Esent.Interop.Vista.JET_THREADSTATS](hh578565\(v=exchg.10\).md)  
A JET_THREADSTATS containing the result of adding the stats in t1 and t2.  

## See also

#### Reference

[JET_THREADSTATS structure](hh578565\(v=exchg.10\).md)

[JET_THREADSTATS members](hh579250\(v=exchg.10\).md)

[Microsoft.Isam.Esent.Interop.Vista namespace](hh558039\(v=exchg.10\).md)

