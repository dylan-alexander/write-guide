---
title: JetGetColumnInfo Function
TOCTitle: JetGetColumnInfo Function
ms:assetid: 2db024e9-2784-4fb2-84b2-fef7ae518938
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg269215(v=EXCHG.10)
ms:contentKeyID: 32765518
ms.date: 04/11/2016
ms.topic: reference
api_name: 
- JetGetColumnInfoA
- JetGetColumnInfoW
- JetGetColumnInfo
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

# JetGetColumnInfo Function


_**Applies to:** Windows | Windows Server_

## JetGetColumnInfo Function

The **JetGetColumnInfo** function retrieves information about a column.

```cpp
    JET_ERR JET_API JetGetColumnInfo(
      __in          JET_SESID sesid,
      __in          JET_DBID dbid,
      __in          const tchar* szTableName,
      __in          const tchar* szColumnName,
      __out         void* pvResult,
      __in          unsigned long cbMax,
      __in          unsigned long InfoLevel
    );
```

### Parameters

*sesid*

The database session context to use for the API call.

*dbid*

Identifies, along with *szTableName*, the table that contains the column from which the information is retrieved.

*szTableName*

Identifies, along with *dbid*, the table that contains the column from which the information is retrieved.

*szColumnName*

The name of the column that information is fetched for.

*pvResult*

Pointer to a buffer that will receive the information. The type of the buffer is dependent on *InfoLevel*. The caller must be configured to align the buffer appropriately.

*cbMax*

The size, in bytes, of the buffer that is passed in *pvResult*.

*InfoLevel*

The type of information to retrieve for the column that is specified by *szColumnName*. The format of the data stored in *pvResult* is dependent on this parameter. For the schema of the temporary table, see [JET_COLUMNLIST](gg269228\(v=exchg.10\).md).

These *InfoLevels* are differentiated by:

  - JET_ColInfoListSortColumnid will sort the temporary table by *columnid*.

  - JET_ColInfoListCompact will compact the output. For more information about the compact output, see [JET_COLUMNLIST](gg269228\(v=exchg.10\).md).

The following options are available for use with this parameter.

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
<td><p>JET_ColInfo</p></td>
<td><p>JET_ColInfo and JET_ColInfoByColid both retrieve the same information. <em>pvResult</em> is interpreted as a <a href="gg294130(v=exchg.10).md">JET_COLUMNDEF</a>, and the fields of the <a href="gg294130(v=exchg.10).md">JET_COLUMNDEF</a> structure are filled in appropriately.</p></td>
</tr>
<tr class="even">
<td><p>JET_ColInfoBase</p></td>
<td><p><em>pvResult</em> is interpreted as a <a href="gg269194(v=exchg.10).md">JET_COLUMNBASE</a> structure. This is similar to a <a href="gg294130(v=exchg.10).md">JET_COLUMNDEF</a> structure. If this function succeeds, the structure is populated with appropriate values. If this function fails, the structure contains undefined data.</p></td>
</tr>
<tr class="odd">
<td><p>JET_ColInfoByColid</p></td>
<td><p>Like JET_ColInfo, <em>pvResult</em> is interpreted as a <a href="gg294130(v=exchg.10).md">JET_COLUMNDEF</a>, except this <em>InfoLevel</em> indicates that the requested column (<em>szColumName</em>) is not the string column name, but a pointer to a <a href="gg294104(v=exchg.10).md">JET_COLUMNID</a>.</p></td>
</tr>
<tr class="even">
<td><p>JET_ColInfoList</p></td>
<td><p><em>pvResult</em> is interpreted as a <a href="gg269228(v=exchg.10).md">JET_COLUMNLIST</a> structure. If this function succeeds, the structure is populated with appropriate values. A temporary table is opened and is identified by the <strong>tableid</strong> member of the <a href="gg269228(v=exchg.10).md">JET_COLUMNLIST</a> structure. The table must be closed with <a href="gg294087(v=exchg.10).md">JetCloseTable</a>. If this function fails, the structure contains undefined data.</p></td>
</tr>
<tr class="odd">
<td><p>JET_ColInfoListCompact</p></td>
<td><p>Same as JET_ColInfoList.</p></td>
</tr>
<tr class="even">
<td><p>JET_ColInfoListSortColumnid</p></td>
<td><p>Same as JET_ColInfoList; however the resulting table is sorted by columnid, instead of column name.</p></td>
</tr>
<tr class="odd">
<td><p>JET_ColInfoSysTabCursor</p></td>
<td><p>JET_ColInfoSysTabCursor is deprecated, and use of it will return JET_errFeatureNotAvailable.</p></td>
</tr>
<tr class="even">
<td><p>JET_ColInfoBaseByColId</p></td>
<td><p>Like JET_ColInfoBase, <em>pvResult</em> is interpreted as a <a href="gg269194(v=exchg.10).md">JET_COLUMNBASE</a>, except this <em>InfoLevel</em> indicates that requested column (<em>szColumName</em>) is not the string column name, but a pointer to a <a href="gg294104(v=exchg.10).md">JET_COLUMNID</a>.</p>
<p><strong>Windows Vista:  </strong>This value is introduced in Windows Vista.</p></td>
</tr>
<tr class="odd">
<td><p>JET_ColInfoGrbitNonDerivedColumnsOnly</p></td>
<td><p>Only return non-derived columns (if the table is derived from a template).</p>
<p>This value can be logically or'd into the <em>InfoLevel</em>, when the base <em>InfoLevel</em> is JET_ColInfoList.</p>
<p><strong>Windows Vista:  </strong>This value is introduced Windows Vista.</p></td>
</tr>
<tr class="even">
<td><p>JET_ColInfoGrbitMinimalInfo</p></td>
<td><p>Only return the column name and columnid of each column.</p>
<p>This value can be logically or'd into the <em>InfoLevel</em>, when the base <em>InfoLevel</em> is JET_ColInfoList.</p>
<p><strong>Windows Vista:  </strong>This value is introduced in Windows Vista.</p></td>
</tr>
<tr class="odd">
<td><p>JET_ColInfoGrbitSortByColumnid</p></td>
<td><p>Sort returned column list by columnid (default is to sort list by column name).</p>
<p>This value can be logically or'd into the <em>InfoLevel</em>, when the base <em>InfoLevel</em> is JET_ColInfoList.</p>
<p><strong>Windows Vista:  </strong>This value is introduced in Windows Vista.</p></td>
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
<td><p>JET_errColumnNotFound</p></td>
<td><p>The column named <em>szColumnName</em> was not found in the table.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errFeatureNotAvailable</p></td>
<td><p>A bad <em>InfoLevel</em> was specified.</p></td>
</tr>
<tr class="even">
<td><p>JET_errInvalidName</p></td>
<td><p>This error can be returned if:</p>
<ul>
<li><p>A bad name for <em>szTableName</em> was given.</p></li>
<li><p>A bad name for <em>szColumnName</em> was given.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>JET_errInvalidParameter</p></td>
<td><p>This error can be returned if:</p>
<ul>
<li><p>A bad <em>InfoLevel</em> was specified.</p></li>
<li><p>A NULL <em>szTableName</em> was passed in.</p></li>
<li><p>The buffer is too small.</p></li>
</ul></td>
</tr>
</tbody>
</table>


#### Remarks

[JetGetTableColumnInfo](gg294061\(v=exchg.10\).md) and **JetGetColumnInfo** both retrieve information about a column. The difference between them is how the table is identified:

  - [JetGetTableColumnInfo](gg294061\(v=exchg.10\).md) identifies a table by *tableid*.

  - **JetGetColumnInfo** identifies a table by *dbid* and *szTableName* combination.

When retrieving data with JET_ColInfoList, JET_ColInfoListSortColumnid, or JET_ColInfoListCompact, a temporary table will be opened. The temporary table contains data, and the [JET_COLUMNLIST](gg269228\(v=exchg.10\).md) structure contains sufficient information to traverse the temporary table. The temporary table must be closed with [JetCloseTable](gg294087\(v=exchg.10\).md).

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
<td><p>Implemented as <strong>JetGetColumnInfoW</strong> (Unicode) and <strong>JetGetColumnInfoA</strong> (ANSI).</p></td>
</tr>
</tbody>
</table>


#### See Also

[Error Handling Parameters](gg269173\(v=exchg.10\).md)  
[Extensible Storage Engine Errors](gg269184\(v=exchg.10\).md)  
[JET_COLUMNBASE](gg269194\(v=exchg.10\).md)  
[JET_COLUMNDEF](gg294130\(v=exchg.10\).md)  
[JET_COLUMNID](gg294104\(v=exchg.10\).md)  
[JET_COLUMNLIST](gg269228\(v=exchg.10\).md)  
[JET_ERR](gg294092\(v=exchg.10\).md)  
[JET_GRBIT](gg294066\(v=exchg.10\).md)  
[JET_SESID](gg269253\(v=exchg.10\).md)  
[JET_TABLEID](gg269182\(v=exchg.10\).md)  
[JetCloseTable](gg294087\(v=exchg.10\).md)  
[JetGetTableColumnInfo](gg294061\(v=exchg.10\).md)

