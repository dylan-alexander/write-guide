---
title: Database Parameters
TOCTitle: Database Parameters
ms:assetid: 8fb68748-8718-4393-9fd6-0d9adaa34844
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg269337(v=EXCHG.10)
ms:contentKeyID: 32765626
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

# Database Parameters


_**Applies to:** Windows | Windows Server_

## Database Parameters

This topic contains parameters that are used for the database.

*JET_paramCheckFormatWhenOpenFail*  
44  

This parameter, when set, will cause [JetInit](gg294068\(v=exchg.10\).md) to return a special error when a database or transaction log from a previous release of the database engine is opened. These errors are:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Error</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>JET_errDatabase200Format</p></td>
<td><p>The database and/or transaction log files were created with the database engine in Windows NT 3.51.</p></td>
</tr>
<tr class="even">
<td><p>JET_errDatabase400Format</p></td>
<td><p>The database and/or transaction log files were created with the database engine in a test release prior to Windows NT Server 4.0.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errDatabase500Format</p></td>
<td><p>The database and/or transaction log files were created with the database engine in Windows NT Server 4.0.</p></td>
</tr>
</tbody>
</table>


**Windows Vista:**  For Windows Vista and later, this parameter is obsolete and does not affect the operation of the database engine.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Boolean</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>False, True</p></td>
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


*JET_paramDatabasePageSize*  
64  

This parameter configures the page size for the database. The page size is the smallest unit of space allocation possible for a database file. The database page size is also very important because it sets the upper limit on the size of an individual record in the database.

**Note** Only one database page size is supported per process at this time. This means that if you are in a single process that contains different applications that use the database engine then they must all agree on a database page size.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>4096</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Integer</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>2048, 4096, 8192</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Global</p></td>
</tr>
<tr class="odd">
<td><p>Set After <a href="gg269354(v=exchg.10).md">JetCreateInstance</a>:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Set after <a href="gg294068(v=exchg.10).md">JetInit</a>:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Physical Layout:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Affects Reliability:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>All</p></td>
</tr>
</tbody>
</table>


*JET_paramDbExtensionSize*  
18  

This parameter controls the amount of space that is added to a database file each time it needs to grow to accommodate more data. The size is in database pages.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>256</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Integer</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>1 – 2147483647</p></td>
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
<td><p>No</p>
<p><strong>Windows Vista:</strong>  For Windows Vista and later: Yes</p></td>
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
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>All</p></td>
</tr>
</tbody>
</table>


*JET_paramEnableIndexChecking*  
45  

When this parameter is true, every database is checked at [JetAttachDatabase](gg294074\(v=exchg.10\).md) time for indexes over Unicode key columns that were built using an older version of the NLS library in the operating system. This must be done because the database engine persists the sort keys generated by [LCMapStringW](https://go.microsoft.com/fwlink/?linkid=180732) and the value of these sort keys change from release to release.

If a primary index is detected to be in this state then [JetAttachDatabase](gg294074\(v=exchg.10\).md) will always fail with JET_errPrimaryIndexCorrupted.

If any secondary indexes are detected to be in this state then there are two possible outcomes. If JET_bitDbDeleteCorruptIndexes was passed to [JetAttachDatabase](gg294074\(v=exchg.10\).md) then these indexes will be deleted and JET_wrnCorruptIndexDeleted will be returned from [JetAttachDatabase](gg294074\(v=exchg.10\).md). These indexes will need to be recreated by your application. If JET_bitDbDeleteCorruptIndexes was not passed to [JetAttachDatabase](gg294074\(v=exchg.10\).md) then the call will fail with JET_errSecondaryIndexCorrupted.

**Note** It is strongly recommended that this parameter be set to True by your application.

**Note** It is very strongly recommended that applications avoid the use of Unicode key columns in their primary key (clustered) indexes.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>False</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Boolean</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>False, True</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Global</p>
<p><strong>Windows Vista:</strong>  For Windows Vista and later: Instance</p></td>
</tr>
<tr class="odd">
<td><p>Set After <a href="gg269354(v=exchg.10).md">JetCreateInstance</a>:</p></td>
<td><p>No</p></td>
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
<td><p>Yes</p></td>
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


*JET_paramEnableIndexCleanup*  
54  

When this parameter is set to true, then the database engine may automatically clean up indexes over Unicode key columns at [JetInit](gg294068\(v=exchg.10\).md) time as necessary to avoid database format changes caused by changes to the NLS library in Windows. Such changes are made routinely to the NLS library to add support for new languages, to add missing characters to a language, to add a collation order to a language, or to fix bugs in the collation order of a language. These changes affect the sort keys produced by [LCMapStringW](https://go.microsoft.com/fwlink/?linkid=180732) which are persisted by the database engine as components of index keys.

It is important to realize that it is possible for the changes to the index to be so great that an incremental cleanup is not possible. In this case, the index will be handled as prescribed by **JET_paramEnableIndexChecking**.

**Note** It is strongly recommended that this parameter and **JET_paramEnableIndexChecking** be set to **True** by your application.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Boolean</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>False, True</p></td>
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
<td><p>No</p>
<p><strong>Windows Vista:</strong>  For Windows Vista and later: Yes</p></td>
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
<td><p>Windows Server 2003 and later releases</p></td>
</tr>
</tbody>
</table>


*JET_paramOneDatabasePerSession*  
102  

When this parameter is true then only one database is allowed to be opened using [JetOpenDatabase](gg269299\(v=exchg.10\).md) by a given session at one time. The temporary database is excluded from this restriction.

**Windows XP and Windows Server 2003:**  This parameter is write only on Windows XP and Windows Server 2003.

**Windows Vista:**  This parameter behaves normally as of Windows Vista.

**Note**  This parameter is write only.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>False</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Boolean</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>False, True</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Global</p></td>
</tr>
<tr class="odd">
<td><p>Set After <a href="gg269354(v=exchg.10).md">JetCreateInstance</a>:</p></td>
<td><p>No</p>
<p><strong>Windows Vista:</strong>  For Windows Vista and later: Yes</p></td>
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


*JET_paramEnableOnlineDefrag*  
35  

This parameter controls the behavior of online defragmentation when initiated using [JetDefragment](gg269317\(v=exchg.10\).md). Please see [JetDefragment](gg269317\(v=exchg.10\).md) for more information.

Windows 2000:  On Windows 2000, this parameter was a simple Boolean that would gate online defragmentation when initiated by [JetDefragment](gg269317\(v=exchg.10\).md). When set to **TRUE**, online defragmentation will be performed on the records of each table in the database.

**Windows XP:**  On Windows XP and later releases, this parameter can be set to one or more of the following options:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Option</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>JET_OnlineDefragDisable</p></td>
<td><p>Do not perform online defragmentation. This is the binary equivalent to the Windows 2000 setting of False for this parameter.</p></td>
</tr>
<tr class="even">
<td><p>JET_OnlineDefragAllOBSOLETE</p></td>
<td><p>Perform full online defragmentation. This is the binary equivalent to the Windows 2000 setting of True for this parameter.</p></td>
</tr>
<tr class="odd">
<td><p>JET_OnlineDefragDatabases</p></td>
<td><p>Perform online defragmentation of the records of each table in the database.</p></td>
</tr>
<tr class="even">
<td><p>JET_OnlineDefragSpaceTrees</p></td>
<td><p>Perform online defragmentation of the space trees of each table in the database.</p></td>
</tr>
<tr class="odd">
<td><p>JET_OnlineDefragStreamingFiles</p></td>
<td><p>This parameter is used to support the Microsoft Exchange infrastructure and is not intended to be used in your application.</p></td>
</tr>
<tr class="even">
<td><p>JET_OnlineDefragAll</p></td>
<td><p>Perform full online defragmentation. This is the conceptual equivalent to the Windows 2000 setting of True for this parameter.</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p><strong>Windows 2000:</strong>  True</p>
<p><strong>Windows XP:  For Windows XP and later:</strong> JET_OnlineDefragAll</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p><strong>Windows 2000:</strong>  Boolean</p>
<p><strong>Windows XP and later:</strong>  JET_GRBIT (integer)</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p><strong>Windows 2000:</strong>  False, True</p>
<p><strong>Windows XP and later:</strong>  0 – JET_OnlineDefragAll</p></td>
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
<td><p>Yes</p></td>
</tr>
<tr class="odd">
<td><p>Affects Physical Layout:</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Reliability:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>Yes</p></td>
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


*JET_paramPageFragment*  
20  

This parameter is the threshold that the database engine uses to control free space fragmentation. The size is in database pages.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>8</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Integer</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>0 – 2147483647</p></td>
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
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>All</p></td>
</tr>
</tbody>
</table>


*JET_paramRecordUpgradeDirtyLevel*  
78

This parameter controls how aggressively the database page cache manager will write a database page that has undergone an in place format conversion. These format conversions occur on the fly as pages are loaded from a database that was created with the Windows 2000 database engine but used by a Windows XP or later release of the database engine.

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
<td><p>0-3</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Global</p></td>
</tr>
<tr class="odd">
<td><p>Set After <a href="gg269354(v=exchg.10).md">JetCreateInstance</a>:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Set after <a href="gg294068(v=exchg.10).md">JetInit</a>:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="odd">
<td><p>Affects Physical Layout:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Affects Reliability:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>Yes</p></td>
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


*JET_paramWaypointLatency*  
153  

The latency (in logs) behind the tip / highest committed log to defer database page flushes. Enabling this latency can allow database recovery in the case of catastrophic loss of the most recent logfile. See JET_bitReplayIgnoreLostLogs.

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
<td><p>0-1023</p></td>
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
<td><p>Yes</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>Windows 7</p></td>
</tr>
</tbody>
</table>


*JET_paramDefragmentSequentialBTrees*  
160  

Turn on/off automatic sequential B-tree defragmentation.

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
<td><p>Boolean</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>0-1</p></td>
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
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Affects Reliability:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>Windows 7</p></td>
</tr>
</tbody>
</table>


*JET_paramDefragmentSequentialBTreesDensityCheckFrequency*  
161  

Determines how frequently B-tree density is checked.

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
<td><p>0-Max Integer</p></td>
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
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Affects Reliability:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>Windows 7</p></td>
</tr>
</tbody>
</table>


*JET_paramIOThrottlingTimeQuanta*  
162  

Max time, in milliseconds, that the I/O throttling mechanism gives a task to run for it to be considered 'completed'.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>125</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Integer</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>0-10000</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Global</p></td>
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
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>Windows 7</p></td>
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

[JetAttachDatabase](gg294074\(v=exchg.10\).md)  
[JetCreateInstance](gg269354\(v=exchg.10\).md)  
[JetDefragment](gg269317\(v=exchg.10\).md)  
[JetInit](gg294068\(v=exchg.10\).md)

