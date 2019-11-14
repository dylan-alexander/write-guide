---
title: Windows7Param.WaypointLatency field (Microsoft.Isam.Esent.Interop.Windows7)
TOCTitle: WaypointLatency field
ms:assetid: F:Microsoft.Isam.Esent.Interop.Windows7.Windows7Param.WaypointLatency
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.isam.esent.interop.windows7.windows7param.waypointlatency(v=EXCHG.10)
ms:contentKeyID: 55104440
ms.date: 07/30/2014
ms.topic: reference
f1_keywords:
- Microsoft.Isam.Esent.Interop.Windows7.Windows7Param.WaypointLatency
dev_langs:
- CSharp
- JScript
- VB
- other
api_name: 
- Microsoft.Isam.Esent.Interop.Windows7.Windows7Param.WaypointLatency
topic_type: 
- apiref
- kbSyntax
api_type: 
- Managed
api_location: 
- Microsoft.Isam.Esent.Interop.dll
ROBOTS: INDEX,FOLLOW

---

# Windows7Param.WaypointLatency field

This parameter sets the number of logs that esent will defer database flushes for. This can be used to increase database recoverability if failures cause logfiles to be lost.

**Namespace:**  [Microsoft.Isam.Esent.Interop.Windows7](hh577573\(v=exchg.10\).md)  
**Assembly:**  Microsoft.Isam.Esent.Interop (in Microsoft.Isam.Esent.Interop.dll)

## Syntax

``` vb
'Declaration
Public Const WaypointLatency As JET_param
'Usage
Dim value As JET_param

value = Windows7Param.WaypointLatency
```

``` csharp
public const JET_param WaypointLatency
```

## See also

#### Reference

[Windows7Param class](dn335429\(v=exchg.10\).md)

[Windows7Param members](dn335315\(v=exchg.10\).md)

[Microsoft.Isam.Esent.Interop.Windows7 namespace](hh577573\(v=exchg.10\).md)

