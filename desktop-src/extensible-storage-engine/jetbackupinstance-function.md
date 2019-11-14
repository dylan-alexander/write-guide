---
title: JetBackupInstance Function
TOCTitle: JetBackupInstance Function
ms:assetid: 82486441-5037-440b-8632-038e953ad870
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg269318(v=EXCHG.10)
ms:contentKeyID: 32765608
ms.date: 04/11/2016
ms.topic: reference
api_name: 
- JetBackupInstanceW
- JetBackupInstanceA
- JetBackupInstance
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

# JetBackupInstance Function


_**Applies to:** Windows | Windows Server_

## JetBackupInstance Function

The **JetBackupInstance** function performs a streaming backup of an instance, including all the attached databases, to a directory. With multiple backup methods supported by the engine, this is the simplest and most encapsulated function.

**Windows XP:  JetBackupInstance** is introduced in Windows XP.

```cpp
    JET_ERR JET_API JetBackupInstance(
      __in          JET_INSTANCE instance,
      __in          JET_PCSTR szBackupPath,
      __in          JET_GRBIT grbit,
      __in          JET_PFNSTATUS pfnStatus
    );
```

### Parameters

*instance*

The instance of the database to backup.

*szBackupPath*

The directory where the backup is stored. If the backup path is NULL to use the function will truncate the logs, if possible.

*grbit*

A group of bits specifying zero or more of the following options.

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
<td><p>Creates a full backup of the database. This allows the preservation of an existing backup in the same directory if the new backup fails.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitBackupIncremental</p></td>
<td><p>Creates an incremental backup as opposed to a full backup. This means that only the log files created since the last full or incremental backup will be backed up.</p></td>
</tr>
<tr class="odd">
<td><p>JET_bitBackupSnapshot</p></td>
<td><p>Reserved for future use.</p></td>
</tr>
</tbody>
</table>


*pfnStatus*

Pointer to the [JET_PFNSTATUS](gg269326\(v=exchg.10\).md) callback function, which provides notification information about the progress of the backup operation.

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
<td><p>A backup is already in progress for the same instance. Multiple backups are not allowed at the same time.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errBackupNotAllowedYet</p></td>
<td><p>The instance is not ready yet for backup as it is initializing.</p></td>
</tr>
<tr class="even">
<td><p>JET_errClientRequestToStopJetService</p></td>
<td><p>The operation cannot complete because all activity on the instance associated with the session has ceased as a result of a call to <a href="gg294108(v=exchg.10).md">JetStopServiceInstance</a>.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInstanceUnavailable</p></td>
<td><p>The operation cannot complete because the instance associated with the session has encountered a fatal error that requires that access to all data be revoked to protect the integrity of that data.</p>
<p><strong>Windows XP:  </strong>This return value is introduced in Windows XP.</p></td>
</tr>
<tr class="even">
<td><p>JET_errInvalidBackup</p></td>
<td><p>An incremental backup is not allowed if circular logging is on.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInvalidGrbit</p></td>
<td><p>The specified options are invalid.</p></td>
</tr>
<tr class="even">
<td><p>JET_errInvalidParameter</p></td>
<td><p>An invalid parameter was passed into the API.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInvalidPath</p></td>
<td><p>The destination path does not exist.</p></td>
</tr>
<tr class="even">
<td><p>JET_errLoggingDisabled</p></td>
<td><p>The instance is running without logging. No backup is allowed.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errLogReadVerifyFailure</p></td>
<td><p>There was a checksum verification error on a log file.</p></td>
</tr>
<tr class="even">
<td><p>JET_errLogWriteFail</p></td>
<td><p>The logging for the instance is temporary or permanently disabled due to an unexpected error.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errNotInitialized</p></td>
<td><p>The operation cannot complete because the instance associated with the session has not been initialized yet.</p></td>
</tr>
<tr class="even">
<td><p>JET_errReadVerifyFailure</p></td>
<td><p>There was a checksum verification error on a database page.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errRestoreInProgress</p></td>
<td><p>The operation cannot complete because a restore operation is in progress on the instance associated with the session.</p></td>
</tr>
<tr class="even">
<td><p>JET_errSessionSharingViolation</p></td>
<td><p>The same session cannot be used for more than one thread at the same time.</p>
<p><strong>Windows XP:  </strong>This return value is introduced in Windows XP.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errTermInProgress</p></td>
<td><p>The operation cannot complete because the instance associated with the session is being shut down.</p></td>
</tr>
</tbody>
</table>


After the function returns success, in the backup directory all the files needed for a restore up to the moment of the backup will be present. If this is a full backup, the files will be the database files and the log files needed to bring the database to a consistent state. If this is an incremental backup, only log files will be added to the directories but the already existing files (databases and log files) together with the new log files will be able to be restored and bring the database back to the state at the moment of the backup.

As a side effect of the backup, the log files which are not longer needed will be truncated.

In the same time, the database headers will be updated with the information when the last backup took place.

On failure, there will not be any files in the backup directory destination so no restore will be possible. In the same time, the current log files will not be truncated.

#### Remarks

The different steps of the backup will have Event Log entries generated including the file names, the log truncation and the final result of the backup.

Incremental backup are possible only after a full backup was taken. Also, incremental backups are possible only if circular logging is turned off. It is recommended that the backup directory should not contain other files then the one involved in the backup or added by a previous successful backup.

The backup directory should exist unless the parameter *JET_paramCreatePathIfNotExist* is set for the instance. For information, see [System Parameters](gg294139\(v=exchg.10\).md).

The backup will do checksum verification on all the used database pages and starting with Windows Server 2003, on the log files as well. This gives an opportunity to estimate the health of the database even for pages which are not read during normal operations. If any such corruption will be encountered, the backup will fail.

During the backup, the current log file will be finished and we will start a new log generation. This will allow copying the needed log files because the last needed one will not be in use anymore.

It is strongly recommended that the backup should not be used for other purposed other then the backup and restored at the engine level. This will minimize the change of getting errors during the backup and restore operations.

#### Requirements

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Client</strong></p></td>
<td><p>Requires Windows Vista or Windows XP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Server</strong></p></td>
<td><p>Requires Windows Server 2008 or Windows Server 2003.</p></td>
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
<td><p>Implemented as <strong>JetBackupInstanceW</strong> (Unicode) and <strong>JetBackupInstanceA</strong> (ANSI).</p></td>
</tr>
</tbody>
</table>


#### See Also

[JET_ERR](gg294092\(v=exchg.10\).md)  
[JET_GRBIT](gg294066\(v=exchg.10\).md)  
[JET_INSTANCE](gg294048\(v=exchg.10\).md)  
[JET_PFNSTATUS](gg269326\(v=exchg.10\).md)  
[JetRestore](gg294093\(v=exchg.10\).md)  
[JetRestore2](gg269313\(v=exchg.10\).md)  
[JetRestoreInstance](gg269306\(v=exchg.10\).md)  
[JetStopServiceInstance](gg294108\(v=exchg.10\).md)  
[System Parameters](gg294139\(v=exchg.10\).md)

