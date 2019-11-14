---
title: JetSetColumn Function
TOCTitle: JetSetColumn Function
ms:assetid: f8877519-86d5-4e59-95a8-1927c70cd6b4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg294137(v=EXCHG.10)
ms:contentKeyID: 32765751
ms.date: 04/11/2016
ms.topic: reference
api_name: 
- JetSetColumn
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

# JetSetColumn Function


_**Applies to:** Windows | Windows Server_

## JetSetColumn Function

The **JetSetColumn** function modifies a single column value in a modified record to be inserted or to update the current record. It can overwrite an existing value, add a new value to a sequence of values in a multi-valued column, remove a value from a sequence of values in a multi-valued column, or update all or part of a long value, a column of type [JET_coltypLongText](gg269213\(v=exchg.10\).md) or [JET_coltypLongBinary](gg269213\(v=exchg.10\).md).

```cpp
    JET_ERR JET_API JetSetColumn(
      __in          JET_SESID sesid,
      __in          JET_TABLEID tableid,
      __in          JET_COLUMNID columnid,
      __in_opt      const void* pvData,
      __in          unsigned long cbData,
      __in          JET_GRBIT grbit,
      __in_opt      JET_SETINFO* psetinfo
    );
```

### Parameters

*sesid*

The session to use for this call.

*tableid*

The cursor to use for this call.

*columnid*

The [JET_COLUMNID](gg294104\(v=exchg.10\).md) of the column to be retrieved. Alternatively, a *columnid* value of 0 (zero) can be given. When *columnid* 0 (zero) is given, all tagged columns, sparse and multi-valued columns, are treated as a single column. This facilitates retrieving all sparse columns that are present in a record.

*pvData*

Input buffer containing data to use for column value.

*cbData*

Size in bytes of the input buffer.

*grbit*

A group of bits that contain the options to be used for this call, which include zero or more of the following:

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
<td><p>JET_bitSetAppendLV</p></td>
<td><p>This option is used to append data to a column of type <a href="gg269213(v=exchg.10).md">JET_coltypLongText</a> or <a href="gg269213(v=exchg.10).md">JET_coltypLongBinary</a>. The same behavior can be achieved by determining the size of the existing long value and specifying <em>ibLongValue</em> in <em>psetinfo</em>. However, it's simpler to use this <em>grbit</em> since knowing the size of the existing column value is not necessary.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitSetOverwriteLV</p></td>
<td><p>This option is used replace the existing long value with the newly provided data. When this option is used, it is as though the existing long value has been set to 0 (zero) length prior to setting the new data.</p></td>
</tr>
<tr class="odd">
<td><p>JET_bitSetRevertToDefaultValue</p></td>
<td><p>This option is only applicable for tagged, sparse or multi-valued columns. It causes the column to return the default column value on subsequent retrieve column operations. All existing column values are removed.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitSetSeparateLV</p></td>
<td><p>This option is used to force a long value, columns of type <a href="gg269213(v=exchg.10).md">JET_coltypLongText</a> or <a href="gg269213(v=exchg.10).md">JET_coltypLongBinary</a>, to be stored separately from the remainder of record data. This occurs normally when the size of the long value prevents it from being stored with remaining record data. However, this option can be used to force the long value to be stored separately. Note that long values four bytes in size of smaller cannot be forced to be separate. In such cases, the option is ignored.</p></td>
</tr>
<tr class="odd">
<td><p>JET_bitSetSizeLV</p></td>
<td><p>This option is used to interpret the input buffer as a integer number of bytes to set as the length of the long value described by the given <em>columnid</em> and if provided, the sequence number in psetinfo-&gt;itagSequence. If the size given is larger than the existing column value, the column will be extended with 0s. If the size is smaller than the existing column value then the value will be truncated.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitSetUniqueMultiValues</p></td>
<td><p>This option is used to enforce that all values in a multi-valued column are distinct. This option compares the source column data, without any transformations, to other existing column values and an error is returned if a duplicate is found. If this option is given, then JET_bitSetAppendLV, JET_bitSetOverwriteLV and JET_bitSetSizeLV cannot also be given.</p></td>
</tr>
<tr class="odd">
<td><p>JET_bitSetUniqueNormalizedMultiValues</p></td>
<td><p>This option is used to enforce that all values in a multi-valued column are distinct. This option compares the key normalized transformation of column data, to other similarly transformed existing column values and an error is returned if a duplicate is found. If this option is given, then JET_bitSetAppendLV, JET_bitSetOverwriteLV and JET_bitSetSizeLV cannot also be given.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitSetZeroLength</p></td>
<td><p>This option is used to set a value to zero length. Normally, a column value is set to <strong>NULL</strong> by passing a cbMax of 0 (zero). However, for some types, like <a href="gg269213(v=exchg.10).md">JET_coltypText</a>, a column value can be 0 (zero) length instead of <strong>NULL</strong>, and this option is used to differentiate between <strong>NULL</strong> and 0 (zero) length.</p>
<p><strong>Note</strong>  In general, if the column is a fixed-length column, this bit is ignored and the column is set to <strong>NULL</strong>. However, if the column is a fixed-length tagged column, the column length is set to 0. When the fixed-length tagged column is set to 0 length, attempts to retrieve the column with <a href="gg269198(v=exchg.10).md">JetRetrieveColumn</a> or <a href="gg294135(v=exchg.10).md">JetRetrieveColumns</a> will succeed, but the actual length that is returned in the <em>cbActual</em> parameter is 0.</p></td>
</tr>
<tr class="odd">
<td><p>JET_bitSetIntrinsicLV</p></td>
<td><p>This option is used to store the entire long value in the record.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitSetCompressed</p></td>
<td><p>This option is used to attempt data compression when storing the data.</p>
<p><strong>Windows 7:</strong>  JET_bitSetCompressed is introduced in Windows 7.</p></td>
</tr>
<tr class="odd">
<td><p>JET_bitSetUncompressed</p></td>
<td><p>This option is used not attempt compression when storing the data.</p>
<p><strong>Windows 7:</strong>  JET_bitSetUnCompressed is introduced in Windows 7.</p></td>
</tr>
</tbody>
</table>


*psetinfo*

Pointer to optional input parameters that can be set for this function using the [JET_SETINFO](gg294090\(v=exchg.10\).md) structure.

If *psetinfo* is given as **NULL** then the function behaves as though an *itagSequence* of 1 and an *ibLongValue* of 0 (zero) were given. This causes column set to set the first value of a multi-valued column, and to set long data beginning at offset 0 (zero).

The following options can be set for this parameter:

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
<td><p>ibLongValue</p></td>
<td><p>Binary offset into a long column value where set data should begin.</p></td>
</tr>
<tr class="even">
<td><p>itagSequence</p></td>
<td><p>Sequence number of the desired multi-valued column value to set. If <em>itagSequence</em> is set to 0 (zero), then the value provided should be appended to then end of the sequence of multi-valued values. If the sequence number provided is greater than the last existing multi-valued value, then again the given value is appended to the end of the sequence of values. If the sequence number corresponds to an existing value then that value is replaced with the given value.</p></td>
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
<td><p>JET_errBadColumnId</p></td>
<td><p>The column ID given is outside the legal limits of a column ID.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errClientRequestToStopJetService</p></td>
<td><p>It is not possible to complete the operation because all activity on the instance associated with the session has ceased as a result of a call to <a href="gg269240(v=exchg.10).md">JetStopService</a>.</p></td>
</tr>
<tr class="even">
<td><p>JET_errColumnNotFound</p></td>
<td><p>The column described by the given <em>columnid</em> does not exist in the table.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errColumnNotUpdatable</p></td>
<td><p>An illegal attempt was made to update a long value during a insert copy delete original update operation.</p></td>
</tr>
<tr class="even">
<td><p>JET_errColumnTooBig</p></td>
<td><p>The given column value data given in the input buffer exceeds the size limitation either natural for a fixed length column or configured for fixed length text or binary columns. This error is also returned when passing more than 1024 bytes of data for a long column and setting the JET_bitSetIntrinsicLV flag.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInstanceUnavailable</p></td>
<td><p>It is not possible to complete the operation because the instance associated with the session has encountered a fatal error that requires that access to all data be revoked to protect the integrity of that data.</p>
<p><strong>Windows XP:</strong>  This error will only be returned by Windows XP and later releases.</p></td>
</tr>
<tr class="even">
<td><p>JET_errInvalidBufferSize</p></td>
<td><p>The given column value data size does not match what is natural for the fixed length data type.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInvalidColumnType</p></td>
<td><p>An illegal attempt was made to update an auto-increment column either during an insert or update operation, or to update a version column during a replace operation.</p></td>
</tr>
<tr class="even">
<td><p>JET_errInvalidgrbit</p></td>
<td><p>The options supplied are unknown or an illegal combination of known bit settings.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInvalidParameter</p></td>
<td><p>The given psetinfo-&gt;cbStruct is not a valid size for the <a href="gg294090(v=exchg.10).md">JET_SETINFO</a> structure.</p></td>
</tr>
<tr class="even">
<td><p>JET_errMultiValuedDuplicate</p></td>
<td><p>The set column operation attempted to create a duplicate value and specified either JET_bitSetUniqueMultiValues or JET_bitSetUniqueNormalizedMultiValues.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errNotInitialized</p></td>
<td><p>It is not possible to complete the operation because the instance associated with the session has not been initialized yet.</p></td>
</tr>
<tr class="even">
<td><p>JET_errNotInTransaction</p></td>
<td><p>An illegal attempt was made to update a long column value when the calling session was not in a transaction.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errNullInvalid</p></td>
<td><p>An illegal attempt was made to set a non-<strong>NULL</strong> column to <strong>NULL</strong>.</p></td>
</tr>
<tr class="even">
<td><p>JET_errColumnIllegalNull</p></td>
<td><p>Same as JET_errNullInvalid.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errRecordTooBig</p></td>
<td><p>The column value could not be set to the value in the input buffer because it would have caused the record to exceed its page size related size limitation. Columns of type <a href="gg269213(v=exchg.10).md">JET_coltypLongText</a> or <a href="gg269213(v=exchg.10).md">JET_coltypLongBinary</a> can be stored separately from the remaining record data. However, other columns must be stored with the record and can cause the record size limitation to be exceeded. Even long columns require 5-bytes of space within the record as a linkage and this too can lead to JET_errRecordTooBig being returned.</p></td>
</tr>
<tr class="even">
<td><p>JET_errRestoreInProgress</p></td>
<td><p>It is not possible to complete the operation because a restore operation is in progress on the instance associated with the session.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errSessionSharingViolation</p></td>
<td><p>The same session cannot be used for more than one thread at the same time.</p>
<p><strong>Windows XP:</strong>  This error will only be returned by Windows XP and later releases.</p></td>
</tr>
<tr class="even">
<td><p>JET_errTermInProgress</p></td>
<td><p>It is not possible to complete the operation because the instance associated with the session is being shut down.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errUpdateNotPrepared</p></td>
<td><p>The cursor is not currently in the process of either inserting a new record or updating an existing record.</p></td>
</tr>
<tr class="even">
<td><p>JET_errVersionStoreOutOfMemory</p></td>
<td><p>This error will occur when the configured size of the version store is insufficient to hold all outstanding updates.</p></td>
</tr>
<tr class="odd">
<td><p>JET_wrnColumnMaxTruncated</p></td>
<td><p>The column value in the input buffer exceeded the maximum configured length for a variable length column and was truncated.</p></td>
</tr>
</tbody>
</table>


On success, the desired portion of a column value for the given column is set with data copied from the input buffer. The data set may have been truncated if it exceeded the maximum length specified for a variable length column.

On failure, the cursor location is left unchanged and no column value data is updated in the copy buffer.

#### Remarks

Setting long values, values for columns [JET_coltypLongBinary](gg269213\(v=exchg.10\).md) of type [JET_coltypLongText](gg269213\(v=exchg.10\).md) or [JET_coltypLongBinary](gg269213\(v=exchg.10\).md), should be done only when the calling session is in a transaction. If the calling session is not in a transaction, modifications to long values which are stored separately may be committed fully even when the update operation is later cancelled. If the calling session is in a transaction, then the effects of the update can be fully rolled back by canceling the update and rolling back the session transaction.

Index updates are not performed as a result of **JetSetColumn** operations. Instead, indexes are updated only after all column modifications are complete and [JetUpdate](gg269288\(v=exchg.10\).md) is called. This permits the most efficient updating of indexes when indexes involve more than one column being modified.

A record is limited in size based on the database page size. Any long values in the record larger than five bytes will be stored separate from the record should the data in the record exceed its limit as a result of a **JetSetColumn** operation. The error JET_errRecordTooBig will only be returned after all separable record column data has been stored separately from the record and the record still exceeds the record size limit.

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

[JET_COLUMNID](gg294104\(v=exchg.10\).md)  
[JET_ERR](gg294092\(v=exchg.10\).md)  
[JET_SESID](gg269253\(v=exchg.10\).md)  
[JET_TABLEID](gg269182\(v=exchg.10\).md)  
[JET_SETINFO](gg294090\(v=exchg.10\).md)  
[JetRetrieveColumn](gg269198\(v=exchg.10\).md)  
[JetSetColumns](gg294050\(v=exchg.10\).md)

