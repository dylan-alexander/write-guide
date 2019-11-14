---
title: JetDefragment2 Function
TOCTitle: JetDefragment2 Function
ms:assetid: cfb190cf-8bd3-4479-a6a1-7c0c9e8c74ca
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg294095(v=EXCHG.10)
ms:contentKeyID: 32765710
ms.date: 04/11/2016
ms.topic: reference
api_name: 
- JetDefragment2
- JetDefragment2A
- JetDefragment2W
topic_type: 
- kbArticle
- apiref
api_type: 
- COM
- DLLExport
api_location: 
- ESENT.DLL
ROBOTS: INDEX,FOLLOW

---

# JetDefragment2 Function


_**Applies to:** Windows | Windows Server_

## JetDefragment2 Function

The **JetDefragment2** function starts and stops database defragmentation tasks which improves data organization within a database, with a callback parameter available to report the progress of the defragmentation. This is done to limit database growth by using existing disk allocation more efficiently within the database. It can also reduce working set by ensuring that data is more closely packed. Lastly, it can improve application performance by speeding common operations through better data organization.

**Windows XP:**  **JetDefragment2** is introduced in Windows XP.

**JetDefragment2** also contains a callback function parameter that is used to report on the progress of the defragmentation process.

Database defragmentation is an online operation and does not interrupt regular database activity such as query operations or data updates. **JetDefragment2** also does not make a copy of all existing data. Instead, it defragments a database in place. Lastly, **JetDefragment2** recovers internal database space for re-use but does not release excess space to the operating system file system.

The resulting format of the data can be much more efficient but is not generally optimal. Defragmentation is limited to releasing database pages for re-use which contain data that has already been logically deleted. Defragmentation also makes database pages available for re-use in some cases by combining data from two pages when it can fit on a single page.

This operation is different from [JetCompact](gg269284\(v=exchg.10\).md) which makes a copy of a read-only database into a highly optimal form.

    JET_ERR JET_API JetDefragment2(
      __in          JET_SESID sesid,
      __in          JET_DBID dbid,
      __in          JET_PCSTR szTableName,
      __out_opt     unsigned long* pcPasses,
      __out_opt     unsigned long* pcSeconds,
      __in          JET_CALLBACK callback,
      __in          JET_GRBIT grbit
    );

### Parameters

*sesid*

The session to use for this call.

*dbid*

The database to defragment.

*szTableName*

Unused parameter. Defragmentation is performed for the entire database described by the given database ID.

*pcPasses*

When starting an online defragmentation task, this optional input parameter sets the maximum number of defragmentation passes. When stopping an online defragmentation task, this optional output buffer is set to the number of passes performed.

When this parameter is set to NULL, the number of online defragmentation passes is unlimited.

*pcSeconds*

When starting an online defragmentation task, this optional input parameter sets the maximum time for defragmentation. When stopping an online defragmentation task, this optional output buffer is set to the length of time used for defragmentation.

When this parameter is set to NULL or if *pcSeconds* points to a negative value, the maximum time for defragmentation is unlimited.

*callback*

Callback function that defragmentation calls regularly to report progress.

*grbit*

A group of bits specifying zero or more of the following options.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Value</p></th>
<th><p>Meaning</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>JET_bitDefragmentAvailSpaceTreesOnly</p></td>
<td><p>This option is used to defragment the available space portion of ESE database space allocation. Database space is divided into two types, owned space and available space. Owned space is allocated to a table or index while available space is ready for use within the table or index, respectively. Available space is much more dynamic in behavior and requires online defragmentation more so than owned space or table or index data.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitDefragmentBatchStart</p></td>
<td><p>This option is used to start a new defragmentation task.</p></td>
</tr>
<tr class="odd">
<td><p>JET_bitDefragmentBatchStop</p></td>
<td><p>This option is used to stop an existing started defragmentation task.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitDefragmentBTree</p></td>
<td><p>This option is used to defrag a B-Tree.</p></td>
</tr>
</tbody>
</table>


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
<td><p>JET_errClientRequestToStopJetService</p></td>
<td><p>It is not possible to complete the operation because all activity on the instance associated with the session has ceased as a result of a call to <a href="gg269240(v=exchg.10).md">JetStopService</a>.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errDatabaseFileReadOnly</p></td>
<td><p>The database chosen for defragmentation is read only and cannot be updated in any way, including defragmentation.</p></td>
</tr>
<tr class="even">
<td><p>JET_errDistributedTransactionAlreadyPreparedToCommit</p></td>
<td><p>The given session is in the prepared to commit state, and cannot begin new updates until the current transaction is committed or rolled back.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInstanceUnavailable</p></td>
<td><p>It is not possible to complete the operation because the instance associated with the session has encountered a fatal error that requires that access to all data be revoked to protect the integrity of that data. This error will only be returned by Windows XP and later releases.</p></td>
</tr>
<tr class="even">
<td><p>JET_errInvalidDatabaseId</p></td>
<td><p>The given database ID does not match a known database in the instance.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errNotInitialized</p></td>
<td><p>It is not possible to complete the operation because the instance associated with the session has not been initialized yet.</p></td>
</tr>
<tr class="even">
<td><p>JET_errRestoreInProgress</p></td>
<td><p>It is not possible to complete the operation because a restore operation is in progress on the instance associated with the session.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errSessionSharingViolation</p></td>
<td><p>The same session cannot be used for more than one thread at the same time. This error will only be returned by Windows XP and later releases.</p></td>
</tr>
<tr class="even">
<td><p>JET_errTermInProgress</p></td>
<td><p>It is not possible to complete the operation because the instance associated with the session is being shut down.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errTransReadOnly</p></td>
<td><p>The given session has read-only privileges only and cannot start a task that may perform an update, including defragmentation.</p></td>
</tr>
<tr class="even">
<td><p>JET_errVersionStoreOutOfMemory</p></td>
<td><p>This error will occur when the configured size of the version store is insufficient to hold all outstanding updates.</p></td>
</tr>
<tr class="odd">
<td><p>JET_wrnDefragAlreadyRunning</p></td>
<td><p>The JET_bitDefragmentBatchStart option has been passed but a defragmentation task is already running defragmentation on the given database.</p></td>
</tr>
<tr class="even">
<td><p>JET_wrnDefragNotRunning</p></td>
<td><p>The JET_bitDefragmentBatchStop option has been passed, but no defragmentation task is currently running.</p></td>
</tr>
</tbody>
</table>


On success, the requested action of either starting a defragmentation task for a given data with given options is performed, or the action of stopping an existing defragmentation task is performed.

On failure, the requested action of either starting or stopping an online defragmentation job is not done. No other side effects occur.

#### Remarks

Online defragmentation is controlled both by a parameter setting, as well as by this API. The default system parameter value is JET_OnlineDefragAll, which means defragmentation is enabled for all supported data structures. However, using [JetSetSystemParameter](gg294044\(v=exchg.10\).md), it is possible to disable online defragmentation, or to selectively enable it for database space trees only, databases only, streaming files only or any combination of these options. If the system setting for on-line defragmentation is to an obsolete setting, **JetDefragment2** will treat the setting as JET_OnlineDefragAll.

There can at most be one task running for each database. The task runs as a thread in the process hosting ESE.

The session used to start the online defragmentation task can be subsequently used for database operations while the defragmentation task continues, because the defragmentation task allocates its own session. The given session is only used to check the permissions associated with the task starting session and is not actually used for the defragmentation operations themselves.

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
<td><p>Implemented as <strong>JetDefragment2W</strong> (Unicode) and <strong>JetDefragment2A</strong> (ANSI).</p></td>
</tr>
</tbody>
</table>


#### See Also

[JET_ERR](gg294092\(v=exchg.10\).md)  
[JET_SESID](gg269253\(v=exchg.10\).md)  
[JetCompact](gg269284\(v=exchg.10\).md)  
[JetDefragment](gg269317\(v=exchg.10\).md)  
[JetSetSystemParameter](gg294044\(v=exchg.10\).md)  
[JetStopService](gg269240\(v=exchg.10\).md)

