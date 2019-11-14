---
title: JET_DBINFOUPGRADE Structure
TOCTitle: JET_DBINFOUPGRADE Structure
ms:assetid: dd8a881a-33b5-4314-8cfb-b1d75ad37b21
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg294114(v=EXCHG.10)
ms:contentKeyID: 32765728
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

# JET_DBINFOUPGRADE Structure


_**Applies to:** Windows | Windows Server_

## JET_DBINFOUPGRADE Structure

The **JET_DBINFOUPGRADE** structure holds information about the upgrade status of the database. This value is retrieved only if **JET_DBINFOUPGRADE** was passed to [JetGetDatabaseInfo](gg294076\(v=exchg.10\).md) or [JetGetDatabaseFileInfo](gg269239\(v=exchg.10\).md). This structure is not required for current operating system versions of the database engine.

```cpp
    typedef struct {
      unsigned long cbStruct;
      unsigned long cbFilesizeLow;
      unsigned long cbFilesizeHigh;
      unsigned long cbFreeSpaceRequiredLow;
      unsigned long  cbFreeSpaceRequiredHigh;
      unsigned long csecToUpgrade;
      union {
        unsigned long ulFlags;
        struct {
          unsigned long fUpgradable  :1;
          unsigned long fAlreadyUpgraded  :1;
        };
      };
    } JET_DBINFOUPGRADE;
```

### Members

**cbStruct**

Set to the size of the **JET_DBINFOUPGRADE** structure, in bytes.

**cbFilesizeLow**

The low **DWORD** that reflects the current file size for the database.

**cbFilesizeHigh**

The high **DWORD** that reflects the current file size for the database.

**cbFreeSpaceRequiredLow**

The low **DWORD** of estimated free disk space required for an in-place upgrade.

**cbFreeSpaceRequiredHigh**

The high **DWORD** of estimated free disk space required for an in-place upgrade.

**csecToUpgrade**

The estimated time required to upgrade, in seconds.

**ulFlags**

A bit field made of zero or more of the following flags: **fUpgradable**, **fAlreadyUpgraded**.

**fUpgradable**

The database is upgradeable.

**fAlreadyUpgraded**

The database is upgraded to the current database format.

### Remarks

A **JET_DBINFOUPGRADE** structure is populated by a call to [JetGetDatabaseInfo](gg294076\(v=exchg.10\).md) or [JetGetDatabaseFileInfo](gg269239\(v=exchg.10\).md). If the function does not succeed, the contents of the structure are undefined.

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

[JET_ERR](gg294092\(v=exchg.10\).md)  
[JET_GRBIT](gg294066\(v=exchg.10\).md)  
[JET_SESID](gg269253\(v=exchg.10\).md)  
[JET_TABLEID](gg269182\(v=exchg.10\).md)  
[JetGetIndexInfo](gg294084\(v=exchg.10\).md)  
[JetGetObjectInfo](gg269232\(v=exchg.10\).md)  
[JetGetTableIndexInfo](gg294102\(v=exchg.10\).md)  
[JetGetTableInfo](gg269177\(v=exchg.10\).md)

