---
title: JetSetSessionContext Function
TOCTitle: JetSetSessionContext Function
ms:assetid: e44efadf-a5c7-408a-ad68-56646b6ea650
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg294124(v=EXCHG.10)
ms:contentKeyID: 32765738
ms.date: 04/11/2016
ms.topic: reference
api_name: 
- JetSetSessionContext
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

# JetSetSessionContext Function


_**Applies to:** Windows | Windows Server_

## JetSetSessionContext Function

The **JetSetSessionContext** function associates a session with the current thread using the given context handle. This association overrides the default engine requirement that a transaction for a given session must occur entirely on the same thread.

```cpp
    JET_ERR JET_API JetSetSessionContext(
      __in          JET_SESID sesid,
      __in          JET_API_PTR ulContext
    );
```

### Parameters

*sesid*

The session to use for this call.

*ulContext*

A unique identifier to which this session will be associated.

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
<td><p>JET_errClientRequestToStopJetService</p></td>
<td><p>The operation cannot complete because all activity on the instance that is associated with the session has ceased as a result of a call to <a href="gg269240(v=exchg.10).md">JetStopService</a>.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errInstanceUnavailable</p></td>
<td><p>The operation cannot complete because the instance that is associated with the session encountered a fatal error that requires that access to all data be revoked to protect the integrity of that data.</p>
<p><strong>Windows XP:</strong>  This return value is introduced in Windows XP.</p></td>
</tr>
<tr class="even">
<td><p>JET_errInvalidParameter</p></td>
<td><p>One of the parameters that was provided contained an unexpected value, or the combination of several parameter values yielded an unexpected result. This error will be returned by <strong>JetSetSessionContext</strong> under the following conditions:</p>
<ul>
<li><p><em>ulContext</em> is NULL</p></li>
<li><p><em>ulContext</em> is -1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>JET_errNotInitialized</p></td>
<td><p>The operation cannot complete because the instance that is associated with the session has not yet been initialized.</p></td>
</tr>
<tr class="even">
<td><p>JET_errRestoreInProgress</p></td>
<td><p>The operation cannot complete because a restore operation is in progress on the instance that is associated with the session.</p></td>
</tr>
<tr class="odd">
<td><p>JET_errSessionContextAlreadySet</p></td>
<td><p>The session could not be associated with the current thread because it has already been associated with a thread.</p></td>
</tr>
<tr class="even">
<td><p>JET_errTermInProgress</p></td>
<td><p>The operation cannot complete because the instance that is associated with the session is being shut down.</p></td>
</tr>
</tbody>
</table>


If this function succeeds, the session will be associated with the current thread. No change to the database state will occur.

If this function fails, the session state will remain unchanged. No change to the database state will occur.

#### Remarks

A session is usually bound to a specific thread for the duration of a transaction. This behavior is designed to help applications detect and prevent the conceptually ill-advised sharing of a single session amongst multiple threads. Sometimes, this simple check does not work with the application's architecture. For example, if the application is hosting server-side objects using a thread pool and transactions span multiple server calls to a given object then this protection may cause some of those calls to fail with JET_errSessionSharingViolation even though the usage pattern is correct. This situation is common for COM object servers.

**JetSetSessionContext** and [JetResetSessionContext](gg269250\(v=exchg.10\).md) solve this problem by making this session sharing check a little more flexible. When the application starts to make a series of ESE API calls using a particular session, it first sets the session context to a given value. This action associates the session to the calling thread. In the given example, this context could be the address of the object that contains the JET session handle. Once the ESE API calls have been made, the application resets the session context. This action disassociates the session from the calling thread. The object and its session can then be used by another thread even if the session has an active transaction.

It is important to note that **JetSetSessionContext** must be called prior to opening a transaction on that session or the association will not work.

**JetSetSessionContext** is thread safe. Multiple threads can try to set a thread context on the same session at the same time and only one will win. This fact can be used by the application as a means to allocate a session from a pool without storing external state about its allocation.

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

[JET_API_PTR](gg269209\(v=exchg.10\).md)  
[JET_ERR](gg294092\(v=exchg.10\).md)  
[JetResetSessionContext](gg269250\(v=exchg.10\).md)  
[JET_SESID](gg269253\(v=exchg.10\).md)  
[JetStopService](gg269240\(v=exchg.10\).md)

