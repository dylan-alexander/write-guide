---
title: Server2003Api.JetOSSnapshotAbort method  (Microsoft.Isam.Esent.Interop.Server2003)
TOCTitle: 'JetOSSnapshotAbort method '
ms:assetid: M:Microsoft.Isam.Esent.Interop.Server2003.Server2003Api.JetOSSnapshotAbort(Microsoft.Isam.Esent.Interop.JET_OSSNAPID,Microsoft.Isam.Esent.Interop.Server2003.SnapshotAbortGrbit)
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.isam.esent.interop.server2003.server2003api.jetossnapshotabort(v=EXCHG.10)
ms:contentKeyID: 55104209
ms.date: 07/30/2014
ms.topic: reference
f1_keywords:
- Microsoft.Isam.Esent.Interop.Server2003.Server2003Api.JetOSSnapshotAbort
dev_langs:
- CSharp
- JScript
- VB
- other
api_name: 
- Microsoft.Isam.Esent.Interop.Server2003.Server2003Api.JetOSSnapshotAbort
topic_type: 
- apiref
- kbSyntax
api_type: 
- Managed
api_location: 
- Microsoft.Isam.Esent.Interop.dll
ROBOTS: INDEX,FOLLOW

---

# Server2003Api.JetOSSnapshotAbort method

Notifies the engine that it can resume normal IO operations after a freeze period ended with a failed snapshot.

**Namespace:**  [Microsoft.Isam.Esent.Interop.Server2003](hh557147\(v=exchg.10\).md)  
**Assembly:**  Microsoft.Isam.Esent.Interop (in Microsoft.Isam.Esent.Interop.dll)

## Syntax

``` vb
'Declaration
Public Shared Sub JetOSSnapshotAbort ( _
    snapid As JET_OSSNAPID, _
    grbit As SnapshotAbortGrbit _
)
'Usage
Dim snapid As JET_OSSNAPID
Dim grbit As SnapshotAbortGrbitServer2003Api.JetOSSnapshotAbort(snapid, _
    grbit)
```

``` csharp
public static void JetOSSnapshotAbort(
    JET_OSSNAPID snapid,
    SnapshotAbortGrbit grbit
)
```

#### Parameters

  - snapid  
    Type: [Microsoft.Isam.Esent.Interop.JET_OSSNAPID](hh558483\(v=exchg.10\).md)  
    
    Identifier of the snapshot session.

<!-- end list -->

  - grbit  
    Type: [Microsoft.Isam.Esent.Interop.Server2003.SnapshotAbortGrbit](hh163377\(v=exchg.10\).md)  
    
    Options for this call.

## See also

#### Reference

[Server2003Api class](dn351277\(v=exchg.10\).md)

[Server2003Api members](dn351196\(v=exchg.10\).md)

[Microsoft.Isam.Esent.Interop.Server2003 namespace](hh557147\(v=exchg.10\).md)

