---
title: Instance class
TOCTitle: Instance class
ms:assetid: T:Microsoft.Isam.Esent.Interop.Instance
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.isam.esent.interop.instance(v=EXCHG.10)
ms:contentKeyID: 55103260
ms.date: 07/30/2014
ms.topic: reference
f1_keywords:
- Microsoft.Isam.Esent.Interop.Instance
dev_langs:
- CSharp
- JScript
- VB
- other
api_name: 
- Microsoft.Isam.Esent.Interop.Instance
topic_type: 
- apiref
- kbSyntax
api_type: 
- Managed
api_location: 
- Microsoft.Isam.Esent.Interop.dll
ROBOTS: INDEX,FOLLOW

---

# Instance class

A class that encapsulates a [JET_INSTANCE](hh564593\(v=exchg.10\).md) in a disposable object. The instance must be closed last and closing the instance releases all other resources for the instance.

## Inheritance hierarchy

[System.Object](https://docs.microsoft.com/dotnet/api/system.object?redirectedfrom=MSDN)  
  [System.Runtime.ConstrainedExecution.CriticalFinalizerObject](https://docs.microsoft.com/dotnet/api/system.runtime.constrainedexecution.criticalfinalizerobject?redirectedfrom=MSDN)  
    [System.Runtime.InteropServices.SafeHandle](https://docs.microsoft.com/dotnet/api/system.runtime.interopservices.safehandle?redirectedfrom=MSDN)  
      [Microsoft.Win32.SafeHandles.SafeHandleZeroOrMinusOneIsInvalid](https://docs.microsoft.com/dotnet/api/microsoft.win32.safehandles.safehandlezeroorminusoneisinvalid?redirectedfrom=MSDN)  
        Microsoft.Isam.Esent.Interop.Instance  

**Namespace:**  [Microsoft.Isam.Esent.Interop](hh596136\(v=exchg.10\).md)  
**Assembly:**  Microsoft.Isam.Esent.Interop (in Microsoft.Isam.Esent.Interop.dll)

## Syntax

``` vb
'Declaration
Public Class Instance _
    Inherits SafeHandleZeroOrMinusOneIsInvalid
'Usage
Dim instance As Instance
```

``` csharp
public class Instance : SafeHandleZeroOrMinusOneIsInvalid
```

## Thread safety

Any public static (Shared in Visual Basic) members of this type are thread safe. Any instance members are not guaranteed to be thread safe.

## See also

#### Reference

[Instance members](dn350944\(v=exchg.10\).md)

[Microsoft.Isam.Esent.Interop namespace](hh596136\(v=exchg.10\).md)

