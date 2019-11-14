---
title: JetPrepareUpdate Function
TOCTitle: JetPrepareUpdate Function
ms:assetid: 90cbaa83-47f2-4a65-b561-3bdecb7fd95a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg269339(v=EXCHG.10)
ms:contentKeyID: 32765628
ms.date: 04/11/2016
ms.topic: reference
api_name: 
- JetPrepareUpdate
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

# JetPrepareUpdate Function


_**Applies to:** Windows | Windows Server_

## JetPrepareUpdate Function

The **JetPrepareUpdate** function is the first operation in performing an update, for the purposes of inserting a new record or replacing an existing record with new values. Updates are done by calling **JetPrepareUpdate**, then calling [JetSetColumn](gg294137\(v=exchg.10\).md) or [JetSetColumns](gg294050\(v=exchg.10\).md) zero or more times and finally by calling [JetUpdate](gg269288\(v=exchg.10\).md) to complete the operation. **JetPrepareUpdate** and [JetUpdate](gg269288\(v=exchg.10\).md) set the boundaries for an update operation and are important in having only the final update state of a record entered into indexes. This is both more efficient, but also required in cases where data must match a valid state through more than on set column operation.

There are a few different options for inserting or replacing records and they are described in more detail below.

```cpp
    JET_ERR JET_API JetPrepareUpdate(
      __in          JET_SESID sesid,
      __in          JET_TABLEID tableid,
      __in          unsigned long prep
    );
```

### Parameters

*sesid*

The session to use for this call.

*tableid*

The cursor to use for this call.

*prep*

The options that can be used to prepare for an update, which include the following.

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
<td><p>JET_prepCancel</p></td>
<td><p>This flag causes <strong>JetPrepareUpdate</strong> to cancel the update for this cursor.</p></td>
</tr>
<tr class="even">
<td><p>JET_prepInsert</p></td>
<td><p>This flag causes the cursor to prepare for an insert of a new record. All the data is initialized to the default state for the record. If the table has an auto-increment column, then a new value is assigned to this record regardless of whether the update ultimately succeeds, fails or is cancelled.</p></td>
</tr>
<tr class="odd">
<td><p>JET_prepInsertCopy</p></td>
<td><p>This flag causes the cursor to prepare for an insert of a copy of the existing record. There must be a current record if this option is used. The initial state of the new record is copied from the current record. Long values that are stored off-record are virtually copied.</p></td>
</tr>
<tr class="even">
<td><p>JET_prepInsertCopyDeleteOriginal</p></td>
<td><p>This flag causes the cursor to prepare for an insert of the same record, and a delete or the original record. It is used in cases in which the primary key has changed.</p></td>
</tr>
<tr class="odd">
<td><p>JET_prepReplace</p></td>
<td><p>This flag causes the cursor to prepare for a replace of the current record. If the table has a version column, then the version column is set to the next value in its sequence. If this update does not complete, then the version value in the record will be unaffected. An update lock is taken on the record to prevent other sessions from updating this record before this session completes.</p></td>
</tr>
<tr class="even">
<td><p>JET_prepReplaceNoLock</p></td>
<td><p>This flag is similar to JET_prepReplace, but no lock is taken to prevent other sessions from updating this record. Instead, this session may receive JET_errWriteConflict when it calls <a href="gg269288(v=exchg.10).md">JetUpdate</a> to complete the update.</p></td>
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
<td><p>JET_errAlreadyPrepared</p></td>
<td><p><strong>JetPrepareUpdate</strong> was called with a valid flag for prep but not JET_prepCancel and the cursor was already in the prepared state.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errClientRequestToStopJetService</p></td>
<td><p>It is not possible to complete the operation because all activity on the instance associated with the session has ceased as a result of a call to <a href="gg269240(v=exchg.10).md">JetStopService</a>.</p></td>
</tr>
<tr class="even">
<td><p>JET_errInstanceUnavailable</p></td>
<td><p>It is not possible to complete the operation because the instance associated with the session has encountered a fatal error that requires that access to all data be revoked to protect the integrity of that data. This error will only be returned by Windows XP and later releases.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInvalidParameter</p></td>
<td><p>The given prep flag is not a valid flag.</p></td>
</tr>
<tr class="even">
<td><p>JET_errNotInitialized</p></td>
<td><p>It is not possible to complete the operation because the instance associated with the session has not been initialized yet.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errNotInTransaction</p></td>
<td><p><strong>JetPrepareUpdate</strong> was called to replace a record which had SLV columns. SLV columns. Please note that SLV columns are a feature not intended for general usage. This feature is used to support the Microsoft Exchange infrastructure and is not intended to be used in your application.</p></td>
</tr>
<tr class="even">
<td><p>JET_errRestoreInProgress</p></td>
<td><p>It is not possible to complete the operation because a restore operation is in progress on the instance associated with the session.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errRollbackError</p></td>
<td><p><strong>JetPrepareUpdate</strong> was called with JET_prepCancel but could not rollback all of the changes made to columns of type JET_coltypLongText and/or columns of type JET_coltypLongBinary.</p></td>
</tr>
<tr class="even">
<td><p>JET_errSessionSharingViolation</p></td>
<td><p>This flag cannot be used with the same session from more than one thread at the same time. This error will only be returned by Windows XP and later releases.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errTermInProgress</p></td>
<td><p>It is not possible to complete the operation because the instance associated with the session is being shut down.</p></td>
</tr>
<tr class="even">
<td><p>JET_errUpdateNotPrepared</p></td>
<td><p><strong>JetPrepareUpdate</strong> was called with JET_prepCancel but the cursor was not in the prepared state.</p></td>
</tr>
</tbody>
</table>


On success, the cursor is changed to the prepared state for the purpose of the desired update, or in the case of JET_prepCancel, the cursor is reverted to the non-prepared state and any changes are discarded.

On failure, the cursor state is left unchanged. If the failure was JET_errRollbackError then the cursor state is changed to the non-prepared state but not all of the changes have been reverted.

#### Remarks

Inserting a copy of a record is an important optimization when records share data of type JET_coltypLongText and/or JET_coltypLongBinary. This data is stored off-record when large and it is possible for multiple records to share the same physical representation of the data. In this case, the data can be updated from either record, but doing so will cause the data to be burst such that each record has its own copy. It is not possible to change data in one record by a modification from another record. Also, it is not possible to block an update of one record by an update of another record. This is a central feature to ESE and is known as Record Level Locking.

[JetUpdate](gg269288\(v=exchg.10\).md) operations which fail leave the cursor in the update prepared state. This is to permit correction to some errors, such as a wrong column value, without requiring the update state to be recreated. This means that in all cases where a cursor abandons an update, it must explicitly call **JetPrepareUpdate** with JET_prepCancel.

#### Requirements

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Client</strong></p></td>
<td><p>Requires Windows Vista, Windows XP, or Windows 2000 Professional.</p></td>
</tr>
<tr class="even">
<td><p><strong>Server</strong></p></td>
<td><p>Requires Windows Server 2008, Windows Server 2003, or Windows 2000 Server.</p></td>
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

[JET_ERR](gg294092\(v=exchg.10\).md)  
[JET_SESID](gg269253\(v=exchg.10\).md)  
[JET_TABLEID](gg269182\(v=exchg.10\).md)  
[JetRetrieveColumn](gg269198\(v=exchg.10\).md)  
[JetSetColumn](gg294137\(v=exchg.10\).md)  
[JetUpdate](gg269288\(v=exchg.10\).md)

