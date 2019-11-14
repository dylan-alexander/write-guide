---
Description: Transactional NTFS (TxF) control codes.
ms.assetid: b66d322a-a971-4219-bb5b-dc69b10b2581
title: TxF Control Codes
ms.topic: article
ms.date: 05/31/2018
---

# TxF Control Codes

\[Microsoft strongly recommends developers utilize alternative means to achieve your application s needs. Many scenarios that TxF was developed for can be achieved through simpler and more readily available techniques. Furthermore, TxF may not be available in future versions of Microsoft Windows. For more information, and alternatives to TxF, please see [Alternatives to using Transactional NTFS](deprecation-of-txf.md).\]

Transactional NTFS (TxF) provides the following control codes.

## In this section



| Control Code                                                                                                 | Description                                                                                                                                                                                                                                                                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**FSCTL\_TXFS\_CREATE\_MINIVERSION**](https://msdn.microsoft.com/en-us/library/Aa364598(v=VS.85).aspx)<br/>                         | Creates a new [miniversion](glossary.md) for the specified file. <br/> Miniversions allow you to refer to a snapshot of the file during a transaction. Miniversions are discarded when a transaction is committed or rolled back.<br/>                                                                                                                                                                      |
| [**FSCTL\_TXFS\_GET\_METADATA\_INFO**](https://msdn.microsoft.com/en-us/library/Aa364600(v=VS.85).aspx)<br/>                          | Retrieves Transacted NTFS (TxF) metadata for a file and the **GUID** of the transaction that has locked the specified file (if the file is locked). <br/>                                                                                                                                                                                                                                                                         |
| [**FSCTL\_TXFS\_GET\_TRANSACTED\_VERSION**](https://msdn.microsoft.com/en-us/library/Aa364601(v=VS.85).aspx)<br/>                | Returns a [**TXFS\_GET\_TRANSACTED\_VERSION**](/windows/desktop/api/WinIoCtl/ns-winioctl-txfs_get_transacted_version) structure. The structure identifies the most recently committed version of the specified file, the version number of the handle. <br/>                                                                                                                                                                                                            |
| [**FSCTL\_TXFS\_LIST\_TRANSACTION\_LOCKED\_FILES**](https://msdn.microsoft.com/en-us/library/Aa364604(v=VS.85).aspx)<br/> | Returns a list of all files currently locked by the specified transaction. If the return value is **ERROR\_MORE\_DATA**, it returns the length of the buffer required to hold the complete list of files at the time of this call.<br/>                                                                                                                                                                                           |
| [**FSCTL\_TXFS\_LIST\_TRANSACTIONS**](https://msdn.microsoft.com/en-us/library/Aa364603(v=VS.85).aspx)<br/>                           | Returns a list of all the transactions currently involved in the specified resource manager.<br/>                                                                                                                                                                                                                                                                                                                                 |
| [**FSCTL\_TXFS\_MODIFY\_RM**](https://msdn.microsoft.com/en-us/library/Aa364605(v=VS.85).aspx)<br/>                                           | Sets the log mode and log parameter information for a secondary resource manager (RM).<br/>                                                                                                                                                                                                                                                                                                                                       |
| [**FSCTL\_TXFS\_QUERY\_RM\_INFORMATION**](https://msdn.microsoft.com/en-us/library/Aa364606(v=VS.85).aspx)<br/>                    | Retrieves information for a resource manager (RM).<br/>                                                                                                                                                                                                                                                                                                                                                                           |
| [**FSCTL\_TXFS\_READ\_BACKUP\_INFORMATION**](https://msdn.microsoft.com/en-us/library/Aa364607(v=VS.85).aspx)<br/>              | Returns Transactional NTFS (TxF) specific information for the specified file.<br/>                                                                                                                                                                                                                                                                                                                                                |
| [**FSCTL\_TXFS\_SAVEPOINT\_INFORMATION**](https://msdn.microsoft.com/en-us/library/Bb736256(v=VS.85).aspx)<br/>                   | The [**FSCTL\_TXFS\_SAVEPOINT\_INFORMATION**](https://msdn.microsoft.com/en-us/library/Bb736256(v=VS.85).aspx) control code controls setting, clearing, and rolling back to the specified savepoint.<br/> To perform this operation, call the [**DeviceIoControl**](https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol) function with the following parameters.<br/>                                                                                                                 |
| [**FSCTL\_TXFS\_TRANSACTION\_ACTIVE**](https://msdn.microsoft.com/en-us/library/Aa364805(v=VS.85).aspx)<br/>                         | Returns a Boolean value that indicates if there were any transactions active on the associated volume when the snapshot was taken. This call is only valid for read-only snapshot volumes.<br/>                                                                                                                                                                                                                                   |
| [**FSCTL\_TXFS\_WRITE\_BACKUP\_INFORMATION**](https://msdn.microsoft.com/en-us/library/Aa364808(v=VS.85).aspx)<br/>            | Writes Transactional NTFS (TxF) specific information to a specified file. The **Buffer** member of the [**TXFS\_WRITE\_BACKUP\_INFORMATION**](/windows/desktop/api/WinIoCtl/ns-winioctl-txfs_write_backup_information) structure must be the **Buffer** member of the [**TXFS\_READ\_BACKUP\_INFORMATION\_OUT**](/windows/desktop/api/WinIoCtl/ns-winioctl-txfs_read_backup_information_out) structure returned by [**FSCTL\_TXFS\_READ\_BACKUP\_INFORMATION**](https://msdn.microsoft.com/en-us/library/Aa364607(v=VS.85).aspx).<br/> |



 

 

 




