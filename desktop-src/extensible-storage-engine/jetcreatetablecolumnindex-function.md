---
title: JetCreateTableColumnIndex Function
TOCTitle: JetCreateTableColumnIndex Function
ms:assetid: 9192614b-20a6-40fb-906a-51fc057e7483
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg269343(v=EXCHG.10)
ms:contentKeyID: 32765632
ms.date: 04/11/2016
ms.topic: reference
api_name: 
- JetCreateTableColumnIndexA
- JetCreateTableColumnIndexW
- JetCreateTableColumnIndex
topic_type: 
- apiref
- kbArticle
api_type: 
- DLLExport
- COM
api_location: 
- ESENT.DLL
ROBOTS: INDEX,FOLLOW

---

# JetCreateTableColumnIndex Function


_**Applies to:** Windows | Windows Server_

## JetCreateTableColumnIndex Function

The **JetCreateTableColumnIndex** function creates a table in an ESE database with an initial set of indexes and an initial set of columns from an array of [JET_TABLECREATE](gg294146\(v=exchg.10\).md) structures. The name **JetCreateTableColumnIndex** comes from the order of creation of the objects. It first creates a table, columns, and then finally indexes.

```cpp
    JET_ERR JET_API JetCreateTableColumnIndex(
      __in          JET_SESID sesid,
      __in          JET_DBID dbid,
      __in_out      JET_TABLECREATE* ptablecreate
    );
```

### Parameters

*sesid*

The database session context to use for the API call.

*dbid*

The database identifier to use for the API call.

*ptablecreate*

A pointer to a [JET_TABLECREATE](gg294146\(v=exchg.10\).md) structure which defines the table to be created. See [JET_TABLECREATE](gg294146\(v=exchg.10\).md) for more details.

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
<td><p>JET_errCallbackNotResolved</p></td>
<td><p>The callback function could not be resolved. The DLL might not have been found, or the function in the DLL might not have been found. With sufficient logging enabled, the event log will provide more details.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errCannotIndex</p></td>
<td><p>An attempt was made to index over an escrow-update or SLV column (note that SLV columns are deprecated).</p></td>
</tr>
<tr class="even">
<td><p>JET_errCannotNestDDL</p></td>
<td><p>If ptablecreate-&gt;grbit specifies JET_bitTableCreateTemplateTable, but ptablecreate-&gt;szTemplateTableName is set to NULL.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errColumnDuplicate</p></td>
<td><p>A column already exists.</p></td>
</tr>
<tr class="even">
<td><p>JET_errColumnNotFound</p></td>
<td><p>An attempt was made to index over a non-existent column. Attempting to conditionally index over a non-existent column can also produce this error.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errColumnRedundant</p></td>
<td><p>An attempt was made to add a redundant column. There should be no more than one autoincrement column, and no more than one version column per table.</p></td>
</tr>
<tr class="even">
<td><p>JET_errDensityInvalid</p></td>
<td><p>This error will be returned if the <strong>ulDensity</strong> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure is set to a number less than 20 or more than 100.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errDDLNotInheritable</p></td>
<td><p>Signifies that the table named in the <strong>szTemplateTableName</strong> member of the <a href="gg294146(v=exchg.10).md">JET_TABLECREATE</a> structure was not marked as a template table (that is, that table did not have JET_bitTableCreateTemplateTable set).</p></td>
</tr>
<tr class="even">
<td><p>JET_errIndexDuplicate</p></td>
<td><p>An attempt to define two identical indexes was made.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errIndexHasPrimary</p></td>
<td><p>An attempt was made to specify more than one primary index for a table. A table must have exactly one primary index. If no primary index is specified, the database engine will transparently create one.</p></td>
</tr>
<tr class="even">
<td><p>JET_errIndexInvalidDef</p></td>
<td><p>An invalid index definition was specified. Some of the possible reasons for receiving this error are:</p>
<ul>
<li><p>A primary index is conditional (that is, the <strong>grbit</strong> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure has JET_bitIndexPrimary set, and <strong>cConditionalColumn</strong> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure is greater than zero).</p></li>
<li><p>Windows Server 2003 and later. Attempting to create a tuple index with tuple limits, but without passing the <strong>ptuplelimits</strong> member in the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure (that is, the <strong>grbit</strong> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure has JET_bitIndexTupleLimits set, but the <strong>ptuplelimits</strong> pointer is NULL).</p></li>
<li><p>Passing in an invalid key definition in the <strong>szKey</strong> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure. See <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> for a discussion of valid definitions.</p></li>
<li><p>Setting the <strong>cbVarSegMac</strong> member in <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> to be greater than JET_cbPrimaryKeyMost (for a primary index) or greater than JET_cbSecondaryKeyMost (for a secondary index).</p></li>
<li><p>Passing an invalid combination for a user-defined Unicode index (one which has the JET_bitIndexUnicode bit set in the <strong>grbit</strong> member of <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a>). Some common causes include the <strong>pidxunicode</strong> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure is NULL, or the LCID specified in the <strong>pidxunicode</strong> structure is invalid.</p></li>
<li><p>Specifying a multi-valued column for a primary index.</p></li>
<li><p>Trying to index too many conditional columns. The <strong>cConditionalColumn</strong> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure must not be greater than JET_ccolKeyMost.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>JET_errIndexTuplesInvalidLimits</p></td>
<td><p>Windows XP and later. A <a href="gg269207(v=exchg.10).md">JET_TUPLELIMITS</a> structure was specified, and its limits are not supported. See the remarks section of the <a href="gg269207(v=exchg.10).md">JET_TUPLELIMITS</a> structure.</p></td>
</tr>
<tr class="even">
<td><p>JET_errIndexTuplesNonUniqueOnly</p></td>
<td><p>Windows XP and later. A tuple index cannot be unique (that is, the <em>grbit</em> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure must not have both JET_bitIndexPrimary and JET_bitIndexUnique set).</p></td>
</tr>
<tr class="odd">
<td><p>JET_errIndexTuplesOneColumnOnly</p></td>
<td><p>Windows XP and later. A tuple index can only be over a single column (that is, if the <strong>grbit</strong> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure has JET_bitIndexTuples set, and the <strong>szKey</strong> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure specifies more than one column).</p></td>
</tr>
<tr class="even">
<td><p>JET_errIndexTuplesSecondaryIndexOnly</p></td>
<td><p>Windows XP and later. A tuple index cannot be a primary index (that is, the <strong>grbit</strong> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure must not have both JET_bitIndexPrimary and JET_bitIndexTuples set).</p></td>
</tr>
<tr class="odd">
<td><p>JET_errIndexTuplesTextColumnsOnly</p></td>
<td><p>Windows XP and later. A tuple index can only be on a text or Unicode column. An attempt to index other columns (such as binary columns) will result in JET_errIndexTuplesTextColumnsOnly.</p></td>
</tr>
<tr class="even">
<td><p>JET_errIndexTuplesVarSegMacNotAllowed</p></td>
<td><p>Windows XP and later. A tuple index does not allow the <strong>cbVarSegMac</strong> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure to be set.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInTransaction</p></td>
<td><p>An attempt was made to create an index without version information while in a transaction.</p></td>
</tr>
<tr class="even">
<td><p>JET_errInvalidCodePage</p></td>
<td><p>The <strong>cp</strong> member of the <a href="gg269252(v=exchg.10).md">JET_COLUMNCREATE</a> structure was not set to a valid code page. The only valid values for text columns are English (1252) and Unicode (1200). A value of 0 means the default will be used (English, 1252).</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInvalidColumnType</p></td>
<td><p>The <strong>coltyp</strong> member of the <a href="gg269252(v=exchg.10).md">JET_COLUMNCREATE</a> structure was not set to a valid column type.</p></td>
</tr>
<tr class="even">
<td><p>JET_errInvalidCreateIndex</p></td>
<td><p>Some of the reasons this error may occur:</p>
<ul>
<li><p>The <strong>rgindexcreate</strong> member of the <a href="gg269203(v=exchg.10).md">JET_TABLECREATE2</a> structure was set to NULL.</p></li>
<li><p>The <strong>rgcolumncreate</strong> member of the <a href="gg269203(v=exchg.10).md">JET_TABLECREATE2</a> structure was set to NULL.</p></li>
<li><p>The <strong>cbStruct</strong> member of a <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure was not set to a valid value.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>JET_errInvalidgrbit</p></td>
<td><p>An invalid combination of <strong>grbit</strong> members was specified in <a href="gg294146(v=exchg.10).md">JET_TABLECREATE</a> or <a href="gg269203(v=exchg.10).md">JET_TABLECREATE2</a>.</p>
<p>The index definition is invalid because the <strong>grbit</strong> member contains inconsistent values. Some possible reasons are:</p>
<ul>
<li><p>A primary index had an ignore bit specified (that is, JET_bitIndexPrimary was passed with JET_bitIndexIgnoreNull, JET_bitIndexIgnoreAnyNull, or JET_bitIndexIgnoreFirstNull).</p></li>
<li><p>An empty index does not ignore any NULL members (that is, the <strong>grbit</strong> member of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure has JET_bitIndexEmpty set, but does not have JET_bitIndexIgnoreAnyNull set).</p></li>
<li><p>Passing in a <a href="gg269214(v=exchg.10).md">JET_CONDITIONALCOLUMN</a> structure with an invalid <strong>grbit</strong> member.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>JET_errInvalidLanguageId</p></td>
<td><p>An invalid Locale ID (LCID) was passed in (either through the <strong>lcid</strong> member of the <a href="gg294097(v=exchg.10).md">JET_UNICODEINDEX</a> structure which is pointed to by the <strong>pidxunicode</strong> member in the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure, or through the <strong>lcid</strong> field of the <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure).</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInvalidParameter</p></td>
<td><p>An invalid parameter was given. Some possible reasons are:</p>
<ul>
<li><p>The <strong>rgcolumncreate</strong> member of the <a href="gg269203(v=exchg.10).md">JET_TABLECREATE2</a> structure is NULL.</p></li>
<li><p>The <strong>cbStruct</strong> member of one of the <a href="gg269252(v=exchg.10).md">JET_COLUMNCREATE</a> structures given in the <strong>rgcolumncreate</strong> member of the <a href="gg269203(v=exchg.10).md">JET_TABLECREATE2</a> structure was not set to sizeof( JET_COLUMNCREATE).</p></li>
<li><p>The <strong>cbKey</strong> member of a <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure is set to zero.</p></li>
<li><p>The <strong>cbStruct</strong> member of a <a href="gg269186(v=exchg.10).md">JET_INDEXCREATE</a> structure is not set to sizeof( JET_INDEXCREATE).</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>JET_errRecordTooBig</p></td>
<td><p>The record is too big. The sum of the <strong>cbMax</strong> member of the <a href="gg269252(v=exchg.10).md">JET_COLUMNCREATE</a> structure for all fixed columns must not exceed a certain value.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errTableDuplicate</p></td>
<td><p>The table already exists.</p></td>
</tr>
<tr class="even">
<td><p>JET_errTooManyColumns</p></td>
<td><p>An attempt was made to add too many columns to the table. A table can have no more than JET_ccolFixedMost fixed columns, no more than JET_ccolVarMost variable-length columns, and no more than JET_ccolTaggedMost tagged columns.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errUnicodeTranslationFail</p></td>
<td><p>An error occurred attempting to normalize a Unicode column. This can be caused by running out of system resources.</p></td>
</tr>
</tbody>
</table>


#### Remarks

Calling **JetCreateTableColumnIndex** is identical to calling [JetCreateTableColumnIndex2](gg294057\(v=exchg.10\).md), with each field in the [JET_TABLECREATE2](gg269203\(v=exchg.10\).md) structure containing the value of the corresponding field of [JET_TABLECREATE](gg294146\(v=exchg.10\).md), with the following exceptions:

  - JET_TABLECREATE2.cbStruct set to sizeof( JET_TABLECREATE2)

  - JET_TABLECREATE2.szCallback set to NULL

  - JET_TABLECREATE2.cbtyp set to 0

See [JetCreateTableColumnIndex2](gg294057\(v=exchg.10\).md) for more details.

Like [JetOpenTable](gg294118\(v=exchg.10\).md), when the application is done using the returned *tableid*, it should usually be closed with [JetCloseTable](gg294087\(v=exchg.10\).md).

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
<tr class="even">
<td><p><strong>Unicode</strong></p></td>
<td><p>Implemented as <strong>JetCreateTableColumnIndexW</strong> (Unicode) and <strong>JetCreateTableColumnIndexA</strong> (ANSI).</p></td>
</tr>
</tbody>
</table>


#### See Also

[JET_DBID](gg269248\(v=exchg.10\).md)  
[JET_ERR](gg294092\(v=exchg.10\).md)  
[JET_GRBIT](gg294066\(v=exchg.10\).md)  
[JET_TABLEID](gg269182\(v=exchg.10\).md)  
[JET_TABLECREATE](gg294146\(v=exchg.10\).md)  
[JET_TABLECREATE2](gg269203\(v=exchg.10\).md)  
[JetAddColumn](gg294122\(v=exchg.10\).md)  
[JetCreateTableColumnIndex](gg269343\(v=exchg.10\).md)  
[JetCreateTableColumnIndex2](gg294057\(v=exchg.10\).md)

