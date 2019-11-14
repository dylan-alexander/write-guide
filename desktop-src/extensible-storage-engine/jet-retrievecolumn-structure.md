---
title: JET_RETRIEVECOLUMN Structure
TOCTitle: JET_RETRIEVECOLUMN Structure
ms:assetid: 8e23bed5-5279-4733-b787-a073a0e8d5a5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg269334(v=EXCHG.10)
ms:contentKeyID: 32765623
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

# JET_RETRIEVECOLUMN Structure


_**Applies to:** Windows | Windows Server_

## JET_RETRIEVECOLUMN Structure

The **JET_RETRIEVECOLUMN** structure contains input and output parameters for [JetRetrieveColumns](gg294135\(v=exchg.10\).md). Fields in the structure describe what column value to retrieve, how to retrieve it, and where to save results.

```cpp
    typedef struct {
      JET_COLUMNID columnid;
      void* pvData;
      unsigned long cbData;
      unsigned long cbActual;
      JET_GRBIT grbit;
      unsigned long ibLongValue;
      unsigned long itagSequence;
      JET_COLUMNID columnidNextTagged;
      JET_ERR err;
    } JET_RETRIEVECOLUMN;
```

### Members

**columnid**

The column identifier for the column to retrieve.

**pvData**

A pointer to begin storing data that is retrieved from the column value.

**cbData**

The size of allocation beginning at **pvData**, in bytes. The retrieve column operation will not store more data at **pvData** than **cbData**.

**cbActual**

The size, in bytes, of data that is retrieved by a retrieve column operation.

**grbit**

A group of bits that contain the options for column retrieval, which include zero or more of the following values.

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
<td><p>JET_bitRetrieveCopy</p></td>
<td><p>Retrieves the modified value instead of the original value. If the value has not been modified, then the original value is retrieved. In this way, a value that has not yet been inserted or updated can be retrieved when a record is inserted or updated.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitRetrieveFromIndex</p></td>
<td><p>Retrieves column values from the index without accessing the record, if possible. In this way, unnecessary loading of records can be avoided when needed data is available from index entries themselves. In cases where the original column value cannot be retrieved from the index, because of irreversible transformations or data truncation, the record will be accessed and the data retrieved as normal. This is a performance option and should only be specified when it is likely that the column value can be retrieved from the index. This option should not be specified if the current index is the clustered index, since the index entries for the clustered, or primary, index are the records themselves. This bit cannot be set if JET_bitRetrieveFromPrimaryBookmark is also set.</p></td>
</tr>
<tr class="odd">
<td><p>JET_bitRetrieveFromPrimaryBookmark</p></td>
<td><p>Retrieves column values from the index bookmark, and can differ from the index value when a column appears both in the primary index and the current index. This option should not be specified if the current index is the clustered, or primary, index. This bit cannot be set if JET_bitRetrieveFromIndex is also set.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitRetrieveTag</p></td>
<td><p>Retrieves the sequence number of a multi-valued column value in pretinfo-&gt;itagSequence. The itagSequence field is often used an input for retrieving multi-valued column values from a record. However, when retrieving values from an index, it is also possible to associate the index entry with a particular sequence number and retrieve this sequence number as well. Retrieving the sequence number can be a costly operation and should only be done if necessary.</p></td>
</tr>
<tr class="odd">
<td><p>JET_ bitRetrieveNull</p></td>
<td><p>Retrieves multi-valued column NULL values. If this option is not specified, multi-valued column NULL values will automatically be skipped.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitRetrieveIgnoreDefault</p></td>
<td><p>Causes a NULL value to be returned when the requested sequence number is 1 and there are no set values for the column in the record. This option affects only multi-valued columns.</p></td>
</tr>
<tr class="odd">
<td><p>JET_bitRetrieveLongId</p></td>
<td><p>This flag is for internal use only and is not intended to be used in your application.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitRetrieveLongValueRefCount</p></td>
<td><p>This flag is for internal use only and is not intended to be used in your application.</p></td>
</tr>
</tbody>
</table>


**ibLongValue**

The offset to the first byte to be retrieved from a column of type [JET_coltypLongBinary](gg269213\(v=exchg.10\).md) or [JET_coltypLongText](gg269213\(v=exchg.10\).md).

**itagSequence**

The sequence number of the values that are contained in a multi-valued column. **itagSequence** here in the **JET_RETRIEVECOLUMN** can be 0. If the **itagSequence** is 0 then the number of instances of a multi-valued column are returned instead of any column data. An **itagSequence** value of 0 cannot be used in calls to [JetRetrieveColumn](gg269198\(v=exchg.10\).md).

**columnidNextTagged**

The **columnid** of the tagged, multi-valued, or sparse column when all tagged columns are retrieved by passing 0 as the **columnid** to [JetRetrieveColumn](gg269198\(v=exchg.10\).md).

**err**

Error codes and warnings returned from the retrieval of the column.

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
</tbody>
</table>


### See Also

[JET_COLTYP](gg269213\(v=exchg.10\).md)  
[JET_COLUMNID](gg294104\(v=exchg.10\).md)  
[JET_ERR](gg294092\(v=exchg.10\).md)  
[JET_GRBIT](gg294066\(v=exchg.10\).md)  
[JET_RETRIEVECOLUMN](gg269334\(v=exchg.10\).md)  
[JetRetrieveColumn](gg269198\(v=exchg.10\).md)  
[JetRetrieveColumns](gg294135\(v=exchg.10\).md)

