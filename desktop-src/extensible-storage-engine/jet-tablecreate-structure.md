---
title: JET_TABLECREATE Structure
TOCTitle: JET_TABLECREATE Structure
ms:assetid: ff06325c-d61e-4239-b2d4-868f557f5f76
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg294146(v=EXCHG.10)
ms:contentKeyID: 32765760
ms.date: 04/11/2016
ms.topic: reference
api_name: 
topic_type: 
- apiref
- kbArticle
api_type: 
- COM
api_location: 
ROBOTS: INDEX,FOLLOW

---

# JET_TABLECREATE Structure


_**Applies to:** Windows | Windows Server_

## JET_TABLECREATE Structure

The **JET_TABLECREATE** structure contains the information that is necessary to create a table populated with columns and indexes in an ESE database. The **JET_TABLECREATE** structure is used by [JetCreateTableColumnIndex](gg269343\(v=exchg.10\).md)

```cpp
    typedef struct tagJET_TABLECREATE {
      unsigned long cbStruct;
      tchar* szTableName;
      tchar* szTemplateTableName;
      unsigned long ulPages;
      unsigned long ulDensity;
      JET_COLUMNCREATE* rgcolumncreate;
      unsigned long cColumns;
      JET_INDEXCREATE* rgindexcreate;
      unsigned long cIndexes;
      JET_GRBIT grbit;
      JET_TABLEID tableid;
      unsigned long cCreated;
    } JET_TABLECREATE;
```

### Members

**cbStruct**

The size of this structure in bytes (for future expansion). It must be set to sizeof( JET_TABLECREATE ) in bytes.

**szTableName**

The name of the table to create.

The name must use meet the following conditions:

  - Have a value less than JET_cbNameMost, not including the terminating NULL.

<!-- end list -->

  - Consist of the following set of characters: 0 through 9, A through Z, a through z, and all other punctuation except for exclamation point (\!), comma (,), opening bracket (\[), and closing bracket (\]), that is, ASCII characters 0x20, 0x22 through 0x2d, 0x2f through 0x5a, 0x5c, and 0x5d through 0x7f.

<!-- end list -->

  - Not begin with a space.

<!-- end list -->

  - Consist of at least one non-space character.

**szTemplateTableName**

The name of an already-existing table from which to inherit base DDL (Data Definition Language). Use of a template table allows for the easy creation of many tables with identical columns and indexes.

**ulPages**

The initial number of database pages to allocate for the table. Specifying a number larger than one can reduce fragmentation if many rows are inserted into this table.

**ulDensity**

The table density, in percentage points. The number must be either 0 or in the range of 20 through 100. Passing 0 means that the default value should be used. The default is 80.

**rgcolumncreate**

An array of [JET_COLUMNCREATE](gg269252\(v=exchg.10\).md) structures, each of which corresponds to a column to be created in the new table.

**cColumns**

The number of [JET_COLUMNCREATE](gg269252\(v=exchg.10\).md) elements in **rgcolumncreate**.

**rgindexcreate**

An array of [JET_INDEXCREATE](gg269186\(v=exchg.10\).md) structures, each of which corresponds to an index to be created in the new table.

**cIndexes**

The number of [JET_INDEXCREATE](gg269186\(v=exchg.10\).md) elements in **rgindexcreate**.

**grbit**

A group of bits that contain the options for this call, which include zero or more of the following values.

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
<td><p>JET_bitTableCreateFixedDDL</p></td>
<td><p>Setting JET_bitTableCreateFixedDDL prevents DDL operations on the table (such as adding or removing columns).</p></td>
</tr>
<tr class="even">
<td><p>JET_bitTableCreateTemplateTable</p></td>
<td><p>Setting JET_bitTableCreateTemplateTable causes the table to be a template table. New tables can then specify the name of this table as their template table. Setting JET_bitTableCreateTemplateTable implies JET_bitTableCreateFixedDDL.</p></td>
</tr>
<tr class="odd">
<td><p>JET_bitTableCreateNoFixedVarColumnsInDerivedTables</p></td>
<td><p>Deprecated. Do not use.</p></td>
</tr>
</tbody>
</table>


**tableid**

An output field that holds the [JET_TABLEID](gg269182\(v=exchg.10\).md) of the new table if the API call succeeds. If the API call fails, the value is undefined.

**cCreated**

An output field that contains the count of objects created if the API call succeeds. If the API call fails, the value is undefined.

The count of objects that are created is equal to the sum of columns, tables, and indexes that are successfully created.

### Requirements

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
<td><p><strong>Unicode</strong></p></td>
<td><p>Implemented as <strong>JET_TABLECREATE_W</strong> (Unicode) and <strong>JET_TABLECREATE_A</strong> (ANSI).</p></td>
</tr>
</tbody>
</table>


### See Also

[JET_CALLBACK](gg294098\(v=exchg.10\).md)  
[JET_CBTYP](gg294071\(v=exchg.10\).md)  
[JET_CONDITIONALCOLUMN](gg269214\(v=exchg.10\).md)  
[JET_ERR](gg294092\(v=exchg.10\).md)  
[JET_GRBIT](gg294066\(v=exchg.10\).md)  
[JET_TABLEID](gg269182\(v=exchg.10\).md)  
[JET_INDEXCREATE](gg269186\(v=exchg.10\).md)  
[JetCreateTable](gg269210\(v=exchg.10\).md)  
[JetCreateTableColumnIndex](gg269343\(v=exchg.10\).md)  
[JetCreateTableColumnIndex2](gg294057\(v=exchg.10\).md)

