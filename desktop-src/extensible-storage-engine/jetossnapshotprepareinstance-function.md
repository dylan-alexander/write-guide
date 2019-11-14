---
title: JetOSSnapshotPrepareInstance Function
TOCTitle: JetOSSnapshotPrepareInstance Function
ms:assetid: b4f06342-633f-47c6-be32-64ec058920fe
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg294064(v=EXCHG.10)
ms:contentKeyID: 32765679
ms.date: 04/11/2016
ms.topic: reference
api_name: 
- JetOSSnapshotPrepareInstance
topic_type: 
- kbArticle
- apiref
api_type: 
- DLLExport
- COM
api_location: 
- ESENT.DLL
ROBOTS: INDEX,FOLLOW

---

# JetOSSnapshotPrepareInstance Function


_**Applies to:** Windows | Windows Server_

## JetOSSnapshotPrepareInstance Function

The **JetOSSnapshotPrepareInstance** function selects a specific instance to be part of the snapshot session.

**Windows Vista:** **JetOSSnapshotPrepareInstance** was introduced in Windows Vista.

    JET_ERR JET_API JetOSSnapshotPrepareInstance(
      __in          JET_OSSNAPID snapId,
      __in          JET_INSTANCE instance,
      __in          const JET_GRBIT grbit
    );

### Parameters

*snapId*

The identifier of the snapshot session.

*instance*

The instance that will be used for this call.

*grbit*

The options for this call. This parameter is reserved for future use. The only valid value is 0 (zero).

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
<td><p>JET_errInvalidParameter</p></td>
<td><p>The snapshot id pointer is <strong>NULL</strong> or the <em>grbit</em> parameter is invalid.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errOSSnapshotInvalidSequence</p></td>
<td><p>A snapshot session is already in progress.</p></td>
</tr>
<tr class="even">
<td><p>JET_errOSSnapshotInvalidSnapId</p></td>
<td><p>The identifier for the snapshot session is not valid.</p></td>
</tr>
</tbody>
</table>


If this function succeeds, the specified instance will be part of the snapshot session.

If this function fails, no change in the engine state occurs.

#### Remarks

The normal API sequence call is: [JetOSSnapshotPrepare](gg269224\(v=exchg.10\).md), optionally followed by one or more calls to **JetOSSnapshotPrepareInstance**, then followed by [JetOSSnapshotFreeze](gg269332\(v=exchg.10\).md). Once the freeze is started, it can be terminated using [JetOSSnapshotThaw](gg269229\(v=exchg.10\).md). At any time after the prepare, the snapshot session can be abruptly terminated with [JetOSSnapshotAbort](gg269265\(v=exchg.10\).md). Event log entries will be generated for the different steps of the snapshot.

If **JetOSSnapshotPrepareInstance** is not called between the start of the session ([JetOSSnapshotPrepare](gg269224\(v=exchg.10\).md)) and the freeze moment ([JetOSSnapshotFreeze](gg269332\(v=exchg.10\).md)), all the running instances in the engine will freeze and become part of the snapshot session. This occurs for two reasons:

  - It simplifies the code for users who want all instances.

  - It allows backward compatibility for the callers of the snapshot APIs.

#### Requirements

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Client</strong></p></td>
<td><p>Requires Windows Vista.</p></td>
</tr>
<tr class="even">
<td><p><strong>Server</strong></p></td>
<td><p>Requires Windows Server 2008.</p></td>
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
</tbody>
</table>


#### See Also

[Error Handling Parameters](gg269173\(v=exchg.10\).md)  
[Extensible Storage Engine Errors](gg269184\(v=exchg.10\).md)  
[JET_ERR](gg294092\(v=exchg.10\).md)  
[JetOSSnapshotAbort](gg269265\(v=exchg.10\).md)  
[JetOSSnapshotEnd](gg294136\(v=exchg.10\).md)  
[JetOSSnapshotFreeze](gg269332\(v=exchg.10\).md)  
[JetOSSnapshotPrepare](gg269224\(v=exchg.10\).md)  
[JetOSSnapshotThaw](gg269229\(v=exchg.10\).md)

