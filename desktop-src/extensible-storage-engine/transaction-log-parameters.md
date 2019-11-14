---
title: Transaction Log Parameters
TOCTitle: Transaction Log Parameters
ms:assetid: 41ade693-2bae-4c84-9339-a68a1b7c23e6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg269235(v=EXCHG.10)
ms:contentKeyID: 32765537
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

# Transaction Log Parameters


_**Applies to:** Windows | Windows Server_

**In this article**  
Transaction Log Parameters  
Requirements  
See Also  

## Transaction Log Parameters

This topic contains parameters that are used for transaction logs.

*JET_paramBaseName*  
3  

This parameter sets the three letter prefix used for many of the files used by the database engine. For example, the checkpoint file is called EDB.CHK by default because EDB is the default base name. The base name can be used to easily distinguish between sets of files that belong to different instances or to different applications.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>&quot;edb&quot;</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>String</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>3 characters</p></td>
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


*JET_paramCircularLog*  
17  

This parameter configures how transaction log files are managed by the database engine.

When circular logging is off, all transaction log files that are generated are retained on disk until they are no longer needed because a full backup of the database has been performed. In this mode, it is possible to restore from an older backup and play forward through all the retained transaction log files such that no data is lost as a result of the disaster that forced the restore. Regular full backups are required to prevent the disk from filling up with transaction log files.

When circular logging is on, only transaction log files that are younger than the current checkpoint are retained on disk. The benefit of this mode is that backups are not required to retire old transaction log files. The tradeoff is that a zero data loss restore is no longer possible.

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
<td><p>Yes</p></td>
</tr>
<tr class="odd">
<td><p>Affects Performance:</p></td>
<td><p>No</p></td>
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


*JET_paramCommitDefault*  
16  

This parameter controls the default action taken when the outermost transaction is committed on a session. Any valid option that can be passed to [JetCommitTransaction](gg269191\(v=exchg.10\).md) can also be made to be the default for all sessions in an instance and/or for a specific session. See [JetCommitTransaction](gg269191\(v=exchg.10\).md) for more details on these options.

This parameter has an impact on the reliability and performance of transactions. Please see [JetCommitTransaction](gg269191\(v=exchg.10\).md) for more details.

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
<td><p>JET_GRBIT (integer)</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>A valid option for JetCommitTransaction</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Instance or Session</p></td>
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


*JET_paramDeleteOldLogs*  
48  

When this parameter is true and the transaction log files pointed to by the log file path (**JET_paramLogFilePath**) are all of an obsolete version then those transaction log files will be automatically deleted.

**Windows 2000:**  Care must be taken with the use of this parameter when upgrading a database from Windows NT to Windows 2000. If the database is not in a consistent state and the old log files are deleted then the contents of the database will be lost.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p><strong>Windows 2000:</strong>  False</p>
<p><strong>Windows XP:</strong>  True</p></td>
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
<td><p>Yes</p></td>
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


*JET_paramIgnoreLogVersion*  
47  

If this parameter is true then the database engine will not validate the transaction log file version number during [JetInit](gg294068\(v=exchg.10\).md).

**Windows XP:**  As of Windows XP, this parameter is obsolete and does not affect the operation of the database engine.

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


*JET_paramLegacyFileNames*  
136  

This parameter provides backwards compatibility with the file naming conventions of earlier releases of the database engine.

The following options are currently supported:

JET_bitESE98FileNames

When this option is present then the database engine will use the following naming conventions for its files:

  - Transaction Log files will use .LOG for their file extension

  - Checkpoint files will use .CHK for their file extension

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>JET_bitESE98FileNames</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>JET_GRBIT (integer)</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>0, JET_bitESE98FileNames</p></td>
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


*JET_paramLogBuffers*  
12  

This parameter will configure the amount of memory used to cache log records before they are written to the transaction log file. The unit for this parameter is the sector size of the volume that holds the transaction log files. The sector size is almost always 512 bytes, so it is safe to assume that size for the unit.

This parameter has an impact on performance. When the database engine is under heavy update load, this buffer can become full very rapidly. A larger cache size for the transaction log file is critical for good update performance under such a high load condition. The default is known to be too small for this case.

**Windows XP and Windows 2000:**  On Windows XP and previous releases, it is not recommended to set this parameter to a number of buffers that is larger (in bytes) than half the size of a transaction log file.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p><strong>Windows 2000, Windows XP, and Windows Server 2003:</strong>  80</p>
<p><strong>Windows Vista:</strong>  126</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Integer</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p><strong>Windows 2000, Windows XP, and Windows Server 2003:</strong>  80 – 2147483647</p>
<p><strong>Windows Vista:</strong>  1 – 2147483647</p></td>
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


*JET_paramLogCheckpointPeriod*  
14  

This parameter configures the database engine to take a checkpoint when the specified number of log file sectors has been generated.

**Windows XP:**  As of Windows XP, this parameter is obsolete and does not affect the operation of the database engine.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>1024</p></td>
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


*JET_paramLogFileCreateAsynch*  
69  

When this parameter is set to true, the database engine will create the next transaction log file as the current transaction log file is consumed. The intent is to minimize the time spent switching from one transaction log file to the next under a heavy update load.

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
<td><p>Windows XP and later releases</p></td>
</tr>
</tbody>
</table>


*JET_paramLogFilePath*  
2 

This parameter indicates the relative or absolute file system path of the folder that will contain the transaction logs for the instance. The path must be terminated with a backslash character, which indicates that the target path is a folder. The transaction log files contain the information required to bring the database files to a consistent state after a crash. They are typically named EDB\*.LOG. The contents of the transaction log files are just as important (if not more so) than the database files themselves. Every effort should be made to protect them.

There will also be additional reserve log files named RES1.LOG and RES2.LOG stored along with the ordinary log files. The contents of these files are not important as their only purpose is to reserve disk space to allow the engine to shut down gracefully in a low disk scenario. These will also be a temporary log file typically named EDBTMP.LOG in this same folder. The contents of this file are not important either. This file is a new log file being prepared for use.

The properties of the host volume of the transaction log files and their placement relative to the other files used by the database engine can dramatically impact performance.

**Note**  If a relative path is specified then it will be relative to the current working directory of the process that hosts the application that is using the database engine.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>&quot;.\&quot;</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Folder Path (string)</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>0 – 246 characters</p></td>
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


*JET_paramLogFileSize*  
11  

This parameter will configure the size of the transaction log files. Each transaction log file is a fixed size. The size is equal to the setting of this system parameter in units of 1024 bytes.

This parameter has an impact on reliability. If the setting is too small then the maximum number of log files (1048575) will be reached much faster. When this happens, the instance must be shutdown cleanly, the existing log files must be deleted, and the instance must be restarted. This action will not only reduce the availability of the application but it will also invalidate any previous backups of the application's database.

This parameter has an impact on performance. If the setting is very large then [JetInit](gg294068\(v=exchg.10\).md) will be slow because the database engine must read the youngest log file (at a minimum) when it initializes. If the setting is very large then it will also take longer to switch between log files. If the setting is very small then more log files will need to be created for a given number of updates which will add more overhead.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>5120</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Integer</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p><strong>Windows 2000, Windows XP, and Windows Server 2003:</strong>  128 – 32768</p>
<p><strong>Windows Vista:</strong>  64 – 32768</p></td>
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
<td><p>Yes</p></td>
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


*JET_paramLogWaitingUserMax*  
15  

This parameter attempts to optimize the flush of the log buffer caused by a durable commit by waiting for a specified number of sessions to wait for a durable commit prior to forcing a flush to occur in the hope that another transaction will share the flush.

**Windows XP:**  As of Windows XP, this parameter is obsolete and does not affect the operation of the database engine.

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
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>All</p></td>
</tr>
</tbody>
</table>


*JET_paramRecovery*  
34  

This parameter is the master switch that controls crash recovery for an instance. If this parameter is set to "On" then ARIES style recovery will be used to bring all databases in the instance to a consistent state in the event of a process or machine crash. If this parameter is set to "Off" then all databases in the instance will be managed without the benefit of crash recovery. That is to say, that if the instance is not shut down cleanly using [JetTerm](gg269298\(v=exchg.10\).md) prior to the process exiting or machine shutdown then the contents of all databases in that instance will be corrupted.

Disabling recovery is useful in special circumstances where it is known that the contents of a database are not useful in the event of a crash. Recovery should be enabled for all other cases.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>&quot;On&quot;</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>String</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>0 – 259 characters</p></td>
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
<td><p>Yes</p></td>
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


*JET_paramSystemPath*  
0  

This parameter indicates the relative or absolute file system path of the folder that will contain the checkpoint file for the instance. The path must be terminated with a backslash character, which indicates that the target path is a folder. The checkpoint file is a simple file maintained per instance that remembers the oldest transaction log file that must be replayed to bring all databases in that instance to a consistent state after a crash. The checkpoint file is typically named EDB.CHK.

**Note**  If a relative path is specified then it will be relative to the current working directory of the process that hosts the application that is using the database engine.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>&quot;.\&quot;</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>Folder Path (string)</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>0 – 246 characters</p></td>
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


*JET_paramWaitLogFlush*  
13 

This parameter attempts to optimize the flush of the log buffer caused by a durable commit by waiting for a specified time period prior to forcing a flush to occur in the hope that another transaction will share the flush.

**Windows XP:**  As of Windows XP, this parameter is obsolete and does not affect the operation of the database engine.

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
<td><p>0 – 2147483647</p></td>
</tr>
<tr class="even">
<td><p>Scope:</p></td>
<td><p>Instance or Session</p></td>
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
<td><p>All</p></td>
</tr>
</tbody>
</table>


*JET_paramLegacyFileNames*  
136  

This parameter is used to specify the file naming compatibility features to maintain with the Windows Server 2003 and previous file naming scheme. For more information about the different files and their naming see [Extensible Storage Engine Files](gg294069\(v=exchg.10\).md).

The JET_bitESE98FileNames ensures the file extension used on the transaction log files and the checkpoint file are the same as that used in Windows Server 2003. Note if upgrading from Windows Server 2003, this bit still need not be specified, as the engine will automatically upgrade the file extensions if JET_paramCircularLog is set to **true**, or maintain the older log extension if JET_paramCircularLog is **false**.

**Note**  To set a bit, the value should first be retrieved, and then "or" in the desired compatibility bit.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Default Value:</p></td>
<td><p>JET_bitESE98FileNames</p></td>
</tr>
<tr class="even">
<td><p>Type:</p></td>
<td><p>JET_GRBIT (integer)</p></td>
</tr>
<tr class="odd">
<td><p>Valid Range:</p></td>
<td><p>JET_bitESE98FileNames</p></td>
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
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Affects Resources:</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Availability:</p></td>
<td><p>Starting with Windows Server 2008 and Windows Vista</p></td>
</tr>
</tbody>
</table>


## Requirements

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


## See Also

[Extensible Storage Engine Files](gg294069\(v=exchg.10\).md)  
[JetCommitTransaction](gg269191\(v=exchg.10\).md)  
[JetCreateInstance](gg269354\(v=exchg.10\).md)  
[JetInit](gg294068\(v=exchg.10\).md)  
[JetTerm](gg269298\(v=exchg.10\).md)

