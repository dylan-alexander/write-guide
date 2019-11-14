---
title: JetCreateInstance Function
TOCTitle: JetCreateInstance Function
ms:assetid: 9d6c8c9f-3d3b-4308-87d3-84b1ef270262
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg269354(v=EXCHG.10)
ms:contentKeyID: 32765641
ms.date: 04/11/2016
ms.topic: reference
api_name: 
- JetCreateInstanceW
- JetCreateInstance
- JetCreateInstanceA
topic_type: 
- apiref
- kbArticle
api_type: 
- COM
- DLLExport
api_location: 
- ESENT.DLL
ROBOTS: INDEX,FOLLOW

---

# JetCreateInstance Function


_**Applies to:** Windows | Windows Server_

## JetCreateInstance Function

The **JetCreateInstance** function allocates a new instance of the database engine for use in a single process.

**Windows XP:  JetCreateInstance** is introduced in Windows XP.

```cpp
    JET_ERR JET_API JetCreateInstance(
      __out         JET_INSTANCE* pinstance,
      __in_opt      const tchar* szInstanceName
    );
```

### Parameters

*pinstance*

The output buffer that receives the newly-created instance.

*szInstanceName*

A unique string identifier for the instance to be created. This string must be unique within a given process hosting the database engine.

**Note** A NULL value is treated as a valid string identifier for an instance. Only one instance may have a NULL string identifier.

### Return Value

This function returns the [JET_ERR](gg294092\(v=exchg.10\).md) datatype with one of the following return codes. For more information about the possible ESE errors, see [Extensible Storage Engine Errors](gg269184\(v=exchg.10\).md) and [Error Handling Parameters](gg269173\(v=exchg.10\).md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Return code</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>JET_errSuccess</p></td>
<td><p>The operation completed successfully.</p></td>
</tr>
<tr class="even">
<td><p>JET_errInstanceNameInUse</p></td>
<td><p>The specified instance name is already in use for this process.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInvalidParameter</p></td>
<td><p>One of the parameters provided contained an unexpected value or contained a value that did not make sense when combined with the value of another parameter. This can happen for <strong>JetCreateInstance</strong> when <em>pinstance</em> is <strong>NULL</strong>.</p></td>
</tr>
<tr class="even">
<td><p>JET_errRunningInOneInstanceMode</p></td>
<td><p>The operation failed because it cannot be used when the database engine is operating in single instance mode (Windows 2000 compatibility mode).</p></td>
</tr>
<tr class="odd">
<td><p>JET_errTooManyInstances</p></td>
<td><p>A new instance could not be created because the maximum number of instances has been reached. The maximum number of supported instances is configured using <a href="gg294044(v=exchg.10).md">JetSetSystemParameter</a> using <em>JET_paramMaxInstances</em>.</p></td>
</tr>
</tbody>
</table>


On success, a new instance will be allocated and the identifier for it will be returned. At this point, all system parameters for the instance will have the values of the global default system parameters. Once an instance will be allocated, it needs to be terminated and/or freed later on.

On failure, an error representing the cause of failure will be returned and no instance will be allocated.

#### Remarks

An instance must be initialized with a call to [JetInit](gg294068\(v=exchg.10\).md) before it can be used by anything other than [JetSetSystemParameter](gg294044\(v=exchg.10\).md).

An instance is destroyed by a call to the [JetTerm](gg269298\(v=exchg.10\).md) function, even if that instance was never initialized using [JetInit](gg294068\(v=exchg.10\).md). The maximum number of instances that may be created at any one time is controlled by [JET_paramMaxInstances](gg269201\(v=exchg.10\).md), which can be configured by a call to [JetSetSystemParameter](gg294044\(v=exchg.10\).md). An instance is the unit of recoverability for the database engine. It controls the life cycle of all the files used to protect the integrity of the data in a set of database files. These files include the checkpoint file and the transaction log files.

If the function succeeds, the database engine will automatically be changed to multi-instance mode as a side effect of this call. If the application desires to allow only one instance in the process then [JetInit](gg294068\(v=exchg.10\).md) should be used to start the database engine in Windows 2000 compatibility mode.

If present, the *szDisplayName* will be used to identify the instance in places like Event Log or towards other callers like backup applications (through functions like [JetGetInstanceInfo](gg294149\(v=exchg.10\).md) or [JetOSSnapshotFreeze](gg269332\(v=exchg.10\).md)). If the display name is not provided, the unique *szInstanceName* will be used instead if present, otherwise an empty string will be returned. If the engine did not have the running mode set, after this call, it will be set to multi-instance mode.

The typical start-up sequence for a process potentially running multiple Jet instances would be:

  - A call to [JetCreateInstance2](gg269202\(v=exchg.10\).md) which will allocate and name the instance.

  - Multiple calls to [JetSetSystemParameter](gg294044\(v=exchg.10\).md) for that instance in order to set different system parameters. Note that some system parameters need to be unique per instance (like [JET_paramSystemPath](gg269235\(v=exchg.10\).md) or [JET_paramLogFilePath](gg269235\(v=exchg.10\).md)) so most likely one will need to set each of those.

  - Start the instance using [JetInit](gg294068\(v=exchg.10\).md) or [JetInit2](gg294065\(v=exchg.10\).md). In order to terminate and/or free an instance, [JetTerm](gg269298\(v=exchg.10\).md), [JetTerm2](gg269223\(v=exchg.10\).md) needs to be used.

If this is the first instance to be started, there are a number of additional steps which will be executed during this call in order to make basic system initialization and configuration. A number of those steps might result in specific errors starting with JET_errOutOfMemory but others as well (see errors above).

#### Requirements

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Client</strong></p></td>
<td><p>Requires Windows Vista or Windows XP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Server</strong></p></td>
<td><p>Requires Windows Server 2008 or Windows Server 2003.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Header</strong></p></td>
<td><p>Declared in Esent.h.</p></td>
</tr>
<tr class="even">
<td><p><strong>Library</strong></p></td>
<td><p>Use ESENT.lib.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DLL</strong></p></td>
<td><p>Requires ESENT.dll.</p></td>
</tr>
<tr class="even">
<td><p><strong>Unicode</strong></p></td>
<td><p>Implemented as <strong>JetCreateInstanceW</strong> (Unicode) and <strong>JetCreateInstanceA</strong> (ANSI).</p></td>
</tr>
</tbody>
</table>


#### See Also

[Extensible Storage Engine Files](gg294069\(v=exchg.10\).md)  
[JET_ERR](gg294092\(v=exchg.10\).md)  
[JET_INSTANCE](gg294048\(v=exchg.10\).md)  
[JetCreateInstance2](gg269202\(v=exchg.10\).md)  
[JetEnableMultiInstance](gg294107\(v=exchg.10\).md)  
[JetGetInstanceInfo](gg294149\(v=exchg.10\).md)  
[JetInit](gg294068\(v=exchg.10\).md)  
[JetInit2](gg294065\(v=exchg.10\).md)  
[JetOSSnapshotFreeze](gg269332\(v=exchg.10\).md)  
[JetSetSystemParameter](gg294044\(v=exchg.10\).md)  
[JetTerm](gg269298\(v=exchg.10\).md)  
[JetTerm2](gg269223\(v=exchg.10\).md)

