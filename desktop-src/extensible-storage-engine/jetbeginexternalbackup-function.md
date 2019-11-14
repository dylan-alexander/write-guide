---
title: JetBeginExternalBackup Function
TOCTitle: JetBeginExternalBackup Function
ms:assetid: 702e6cbf-4648-40f2-b2eb-6194759d4cde
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg269292(v=EXCHG.10)
ms:contentKeyID: 32765584
ms.date: 04/11/2016
ms.topic: reference
api_name: 
- JetBeginExternalBackup
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

# JetBeginExternalBackup Function


_**Applies to:** Windows | Windows Server_

## JetBeginExternalBackup Function

The **JetBeginExternalBackup** function initiates an external backup while the engine and database is online and active. **JetBeginExternalBackup** is the first in a series of functions that must be called to execute a successful online (non-VSS based) backup.

An external backup can be used to implement full, incremental, or differential backups.

The backup will be fuzzy, in that the backup will be consistent to a single point in time in the transaction history, but controlling the exact point in time is not possible.

```cpp
    JET_ERR JET_API JetBeginExternalBackup(
      __in          JET_GRBIT grbit
    );
```

### Parameters

*grbit*

A group of bits that specify zero or more of the following options.

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
<td><p>JET_bitBackupAtomic</p></td>
<td><p>This flag is deprecated. Usage of this bit will result in JET_errInvalidgrbit being returned.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitBackupIncremental</p></td>
<td><p>Creates an incremental backup as opposed to a full backup. This means that only the log files since the last full or incremental backup will be backed up.</p></td>
</tr>
<tr class="odd">
<td><p>JET_bitBackupSnapshot</p></td>
<td><p>Reserved for future use. Defined for Windows XP.</p></td>
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
<td><p>JET_errBackupInProgress</p></td>
<td><p>If an external backup or snapshot backup is already in process, this error will be returned, until <strong>JetBeginExternalBackup</strong> (or one of the variants of it) is called. ESE allows only one online backup at a time.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errBackupNotAllowedYet</p></td>
<td><p>The instance or database engine is either in recovery or in a shutdown or termination phase.</p></td>
</tr>
<tr class="even">
<td><p>JET_errCheckpointCorrupt</p></td>
<td><p>On a full backup, the checkpoint file could not be read, or the file could not be verified.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errCheckpointFileNotFound</p></td>
<td><p>On a full backup, the checkpoint file could not be found.</p></td>
</tr>
<tr class="even">
<td><p>JET_errClientRequestToStopJetService</p></td>
<td><p>The operation cannot complete because all activity on the instance that is associated with the session has ceased as a result of a call to <a href="gg269240(v=exchg.10).md">JetStopService</a>.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInstanceUnavailable</p></td>
<td><p>The operation cannot complete because the instance that is associated with the session has encountered a fatal error that requires that access to all data be revoked to protect the integrity of that data.</p>
<p><strong>Windows XP:  </strong>This return value is introduced in Windows XP.</p></td>
</tr>
<tr class="even">
<td><p>JET_errInvalidBackup</p></td>
<td><p>Circular logging is enabled and the backup type specified is JET_bitBackupIncremental. See <a href="gg269235(v=exchg.10).md">JET_paramCircularLog</a> in the <strong>Transaction Log Errors</strong> for information about how to control circular or non-circular logging.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInvalidgrbit</p></td>
<td><p>One or more of the <em>grbit</em> members was invalid.</p></td>
</tr>
<tr class="even">
<td><p>JET_errLoggingDisabled</p></td>
<td><p>Recovery or logging is disabled. You cannot do an online backup if logging is disabled. For more information about logging and recovery, see <a href="gg269235(v=exchg.10).md">JET_paramRecovery</a>.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errLogWriteFail</p></td>
<td><p>The engine has stopped writing to the log drive, due to log being full or disk IO errors.</p></td>
</tr>
<tr class="even">
<td><p>JET_errMissingFullBackup</p></td>
<td><p>The incremental backup was specified (with JET_bitBackupIncremental), and never was a full backup taken for one of the attached databases for the logging set.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errNotInitialized</p></td>
<td><p>The operation cannot complete because the instance that is associated with the session has not yet been initialized.</p></td>
</tr>
<tr class="even">
<td><p>JET_errOutOfMemory</p></td>
<td><p>The operation failed because not enough memory could be allocated to complete it.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errRestoreInProgress</p></td>
<td><p>The operation cannot complete because a restore operation is in progress on the instance associated with the session.</p></td>
</tr>
<tr class="even">
<td><p>JET_errRunningInMultiInstanceMode</p></td>
<td><p>The operation failed because an attempt was made to use the engine in legacy mode (Windows 2000 compatibility mode) where only one instance is supported when in fact multiple instances already exist.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errTermInProgress</p></td>
<td><p>The operation cannot complete because the instance that is associated with the session is being shut down.</p></td>
</tr>
</tbody>
</table>


If the function succeeds, an external backup is initiated and the backup state engine is initialized. Subsequent APIs can now be called to complete the external backup sequence and stream or read off the database file, the database patch file (if supported), and the log file. An event can be logged that an external backup has begun.

If the function fails, the backup session will not be initiated. If another backup session is in progress, it will not be cancelled.

#### Remarks

The external backup process (as started by **JetBeginExternalBackup**) is designed to allow a fuzzy transaction online backup of the entire instance to a target device as a stream. The backup will contain all the database files that are attached to the instance using [JetAttachDatabase](gg294074\(v=exchg.10\).md) (for a full backup), followed by their associated database patch files (if supported), and finally by the transaction log files that were generated during the backup process. The end result will be a set of files that can be restored from the stream, possibly combined with existing database and log files, and finally recovered to a consistent state.

The general order of operations for a full backup consists of the following calls. First, **JetBeginExternalBackup** is called to start the backup process. Then, [JetGetAttachInfo](gg269286\(v=exchg.10\).md) is called to get the list of databases that are attached to the instance that needs to be backed up. For each of these databases, [JetOpenFile](gg269249\(v=exchg.10\).md) is called, followed by a number of [JetReadFile](gg269257\(v=exchg.10\).md) calls, and then by a call to [JetCloseFile](gg294127\(v=exchg.10\).md). Then, [JetGetLogInfo](gg294055\(v=exchg.10\).md) is called to get a list of database patch and log files to be backed up. For each of these files, another sequence of [JetOpenFile](gg269249\(v=exchg.10\).md), [JetReadFile](gg269257\(v=exchg.10\).md), and [JetCloseFile](gg294127\(v=exchg.10\).md) calls are made. Then, any undesired transaction log files are deleted using [JetTruncateLog](gg269263\(v=exchg.10\).md). Finally, the backup is ended by a call to [JetEndExternalBackup](gg269176\(v=exchg.10\).md).

It is also possible to modify this set of steps to perform an incremental backup of the instance. An incremental backup enumerates and backs up log files. Incremental backups are only possible if circular logging is not enabled.

It is also possible to modify this set of steps to allow subsequent differential backups of the instance to be performed. To perform a differential backup, do not call [JetTruncateLog](gg269263\(v=exchg.10\).md) in the previous full or incremental backup. By not calling [JetTruncateLog](gg269263\(v=exchg.10\).md), you enable subsequent backups to be differential with respect to the last full or incremental backup. Differential backups are only possible if circular logging is not enabled.

The database patch file is a special auxiliary file that is used to store database page images under certain circumstances during the backup. This file must be present in the same location as its associated database during a restore operation. This file is only used in Windows 2000. As a result, any application that is written to work against Windows 2000 and other releases must support database patch files, if they are present, but also must not fail if they are not present.

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
[JET_GRBIT](gg294066\(v=exchg.10\).md)  
[JET_INSTANCE](gg294048\(v=exchg.10\).md)  
[JetAttachDatabase](gg294074\(v=exchg.10\).md)  
[JetBeginExternalBackupInstance](gg294132\(v=exchg.10\).md)  
[JetCloseFile](gg294127\(v=exchg.10\).md)  
[JetEndExternalBackup](gg269176\(v=exchg.10\).md)  
[JetEndExternalBackupInstance2](gg294047\(v=exchg.10\).md)  
[JetGetAttachInfo](gg269286\(v=exchg.10\).md)  
[JetGetLogInfo](gg294055\(v=exchg.10\).md)  
[JetOpenFile](gg269249\(v=exchg.10\).md)  
[JetReadFile](gg269257\(v=exchg.10\).md)  
[JetStopBackup](gg294067\(v=exchg.10\).md)  
[JetTruncateLog](gg269263\(v=exchg.10\).md)

