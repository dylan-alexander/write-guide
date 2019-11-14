---
title: EsentCheckpointDepthTooDeepException class
TOCTitle: EsentCheckpointDepthTooDeepException class
ms:assetid: T:Microsoft.Isam.Esent.Interop.EsentCheckpointDepthTooDeepException
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.isam.esent.interop.esentcheckpointdepthtoodeepexception(v=EXCHG.10)
ms:contentKeyID: 55101222
ms.date: 07/30/2014
ms.topic: reference
f1_keywords:
- Microsoft.Isam.Esent.Interop.EsentCheckpointDepthTooDeepException
dev_langs:
- CSharp
- JScript
- VB
- other
api_name: 
- Microsoft.Isam.Esent.Interop.EsentCheckpointDepthTooDeepException
topic_type: 
- apiref
- kbSyntax
api_type: 
- Managed
api_location: 
- Microsoft.Isam.Esent.Interop.dll
ROBOTS: INDEX,FOLLOW

---

# EsentCheckpointDepthTooDeepException class

Base class for JET_err.CheckpointDepthTooDeep exceptions.

## Inheritance hierarchy

[System.Object](https://docs.microsoft.com/dotnet/api/system.object?redirectedfrom=MSDN)  
  [System.Exception](https://docs.microsoft.com/dotnet/api/system.exception?redirectedfrom=MSDN)  
    [Microsoft.Isam.Esent.EsentException](dn292088\(v=exchg.10\).md)  
      [Microsoft.Isam.Esent.Interop.EsentErrorException](dn274314\(v=exchg.10\).md)  
        [Microsoft.Isam.Esent.Interop.EsentOperationException](dn319727\(v=exchg.10\).md)  
          Microsoft.Isam.Esent.Interop.EsentCheckpointDepthTooDeepException  

**Namespace:**  [Microsoft.Isam.Esent.Interop](hh596136\(v=exchg.10\).md)  
**Assembly:**  Microsoft.Isam.Esent.Interop (in Microsoft.Isam.Esent.Interop.dll)

## Syntax

``` vb
'Declaration
<SerializableAttribute> _
Public NotInheritable Class EsentCheckpointDepthTooDeepException _
    Inherits EsentOperationException
'Usage
Dim instance As EsentCheckpointDepthTooDeepException
```

``` csharp
[SerializableAttribute]
public sealed class EsentCheckpointDepthTooDeepException : EsentOperationException
```

## Thread safety

Any public static (Shared in Visual Basic) members of this type are thread safe. Any instance members are not guaranteed to be thread safe.

## See also

#### Reference

[EsentCheckpointDepthTooDeepException members](dn274137\(v=exchg.10\).md)

[Microsoft.Isam.Esent.Interop namespace](hh596136\(v=exchg.10\).md)

