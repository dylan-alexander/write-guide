---
title: Index Parameters
TOCTitle: Index Parameters
ms:assetid: df3dfbc7-71fb-4ae2-a94a-b00eaa1572ec
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg294119(v=EXCHG.10)
ms:contentKeyID: 32765733
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

# Index Parameters


_**Applies to:** Windows | Windows Server_

## Index Parameters

This topic contains parameters that are used for the index.

*JET_paramIndexTupleIncrement*  
132  

This parameter specifies the default for the offset increment used to step through the source column value while generating each tuple. For more information, see the [JET_TUPLELIMITS](gg269207\(v=exchg.10\).md) structure.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Integer</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>0 - 32767</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Instance</p></td>
</tr>
<tr class="odd">
<td><p>Set After <a href="gg269354(v=exchg.10).md">JetCreateInstance</a>:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Set after <a href="gg294068(v=exchg.10).md">JetInit</a>:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Physical Layout:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Reliability:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>Windows Vista and later releases</p></td>
</tr>
</tbody>
</table>


*JET_paramIndexTupleStart*  
133  

This parameter specifies the default for the offset in the source column value at which tuple generation will start. For more information, see the [JET_TUPLELIMITS](gg269207\(v=exchg.10\).md) structure.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>0</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Integer</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>0 - 32767</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Instance</p></td>
</tr>
<tr class="odd">
<td><p>Set After <a href="gg269354(v=exchg.10).md">JetCreateInstance</a>:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Set after <a href="gg294068(v=exchg.10).md">JetInit</a>:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Physical Layout:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Reliability:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>Windows Vista and later releases</p></td>
</tr>
</tbody>
</table>


*JET_paramIndexTuplesLengthMax*  
111  

This parameter specifies the default for the maximum tuple length in a tuple index. For more information, see the [JET_TUPLELIMITS](gg269207\(v=exchg.10\).md) structure.

**Windows Vista:**  Prior to Windows Vista, setting this parameter to zero would set it back to its default value. For Windows Vista, this is no longer supported.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>10</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Integer</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p><strong>Windows 2000, Windows XP and Windows Server 2003: </strong>  0, 2-255</p>
<p><strong>Windows Vista:</strong>  2-255</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Instance</p></td>
</tr>
<tr class="odd">
<td><p>Set After <a href="gg269354(v=exchg.10).md">JetCreateInstance</a>:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Set after <a href="gg294068(v=exchg.10).md">JetInit</a>:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Physical Layout:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Reliability:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>Windows XP and later releases</p></td>
</tr>
</tbody>
</table>


*JET_paramIndexTuplesLengthMin*  
110  

This parameter specifies the default for the minimum tuple length in a tuple index. See [JET_TUPLELIMITS](gg269207\(v=exchg.10\).md) for more information.

**Windows Vista:**  Prior to Windows Vista, setting this parameter to zero would set it back to its default value. For Windows Vista, this is no longer supported.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Integer</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p><strong>Windows 2000, Windows XP and Windows Server 2003: </strong>  0, 2-255</p>
<p><strong>Windows Vista:</strong>  2-255</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Instance</p></td>
</tr>
<tr class="odd">
<td><p>Set After <a href="gg269354(v=exchg.10).md">JetCreateInstance</a>:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Set after <a href="gg294068(v=exchg.10).md">JetInit</a>:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Physical Layout:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Reliability:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>Windows XP and later releases</p></td>
</tr>
</tbody>
</table>


*JET_paramIndexTuplesToIndexMax*  
112  

This parameter specifies the default for the maximum length of a source string to break into tuples for a tuple index. See [JET_TUPLELIMITS](gg269207\(v=exchg.10\).md) for more information.

**Windows Vista:**  Prior to Windows Vista, setting this parameter to zero would set it back to its default value. For Windows Vista, this is no longer supported.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>32767</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Integer</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p><strong>Windows 2000, Windows XP and Windows Server 2003:</strong>  0 – 32767</p>
<p><strong>Windows Vista:</strong>  1 – 32767</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Instance</p></td>
</tr>
<tr class="odd">
<td><p>Set After <a href="gg269354(v=exchg.10).md">JetCreateInstance</a>:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Set after <a href="gg294068(v=exchg.10).md">JetInit</a>:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Physical Layout:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Reliability:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>Windows XP and later releases</p></td>
</tr>
</tbody>
</table>


*JET_paramUnicodeIndexDefault*  
72  

This parameter controls the default Unicode parameters used by any index over a Unicode key column. The type of this parameter is [JET_UNICODEINDEX](gg294097\(v=exchg.10\).md) and is actually passed using a buffer pointer stored in the integer parameter of [JetGetSystemParameter](gg269291\(v=exchg.10\).md) and [JetSetSystemParameter](gg294044\(v=exchg.10\).md). The size of the buffer must equal the size of [JET_UNICODEINDEX](gg294097\(v=exchg.10\).md) and must be passed to [JetGetSystemParameter](gg269291\(v=exchg.10\).md) using the string buffer size parameter. This is clearly inconsistent but that is the behavior of this parameter.

The default value of this parameter contains an LCID for the U.S. English locale and the following [LCMapStringW](https://go.microsoft.com/fwlink/?linkid=180732)flags: LCMAP_SORTKEY, NORM_IGNORECASE, NORM_IGNOREKANATYPE, and NORM_IGNOREWIDTH.

**Windows 2000:**  The SORTID in the LCID is ignored. A SORTID of SORT_DEFAULT is always used.

**Windows 2000:**  The [LCMapStringW](https://go.microsoft.com/fwlink/?linkid=180732) flags must contain the following flags: LCMAP_SORTKEY, NORM_IGNORECASE, NORM_IGNOREKANATYPE, and NORM_IGNOREWIDTH. In addition, the [LCMapStringW](https://go.microsoft.com/fwlink/?linkid=180732)flags may contain the following flags: NORM_IGNORENONSPACE.

**Note**  If your application wishes to store Unicode data, then it is strongly recommended that you do not rely on the default Unicode parameters for your indexes. The use of U.S. English is tantamount to using the invariant locale and the default [LCMapStringW](https://go.microsoft.com/fwlink/?linkid=180732)flags are known to seriously interfere with some languages. You should always specify your own settings for the Unicode parameters to JetCreateIndex2 using [JET_INDEXCREATE](gg269186\(v=exchg.10\).md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>Special</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>JET_UNICODEINDEX* (JET_UNICODEINDEX)</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>Special</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Instance</p></td>
</tr>
<tr class="odd">
<td><p>Set After <a href="gg269354(v=exchg.10).md">JetCreateInstance</a>:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Set after <a href="gg294068(v=exchg.10).md">JetInit</a>:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Physical Layout:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Reliability:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>All</p></td>
</tr>
</tbody>
</table>


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

[JET_INDEXCREATE](gg269186\(v=exchg.10\).md)  
[JET_TUPLELIMITS](gg269207\(v=exchg.10\).md)  
[JET_UNICODEINDEX](gg294097\(v=exchg.10\).md)  
[JetCreateInstance](gg269354\(v=exchg.10\).md)  
[JetGetSystemParameter](gg269291\(v=exchg.10\).md)  
[JetInit](gg294068\(v=exchg.10\).md)  
[JetSetSystemParameter](gg294044\(v=exchg.10\).md)

