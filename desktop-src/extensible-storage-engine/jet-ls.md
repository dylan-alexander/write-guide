---
title: JET_LS
TOCTitle: JET_LS
ms:assetid: 8e4e7902-84b1-404b-8654-bb430a0952aa
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg269336(v=EXCHG.10)
ms:contentKeyID: 32765625
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

# JET_LS


_**Applies to:** Windows | Windows Server_

## JET_LS

The **JET_LS** data type contains a context handle to local storage (LS).This handle might be associated with a cursor or a table and might refer to dynamically allocated resources.

**Windows XP:  JET_LS** is introduced in Windows XP.

```cpp
    typedef JET_API_PTR JET_LS;
```

### Data Types

JET_LS

A value of JET_LSNil indicates an invalid context handle.

### Remarks

A context handle is initially associated with the **JET_LS** data type, using [JetSetLS](gg269243\(v=exchg.10\).md). The context handle can be retrieved from the **JET_LS** data type, using [JetGetLS](gg269234\(v=exchg.10\).md).

The context handle can be explicitly disassociated from the **JET_LS** data type using [JetGetLS](gg269234\(v=exchg.10\).md) with JET_bitLSReset. Alternatively, the context handle can be implicitly disassociated from the **JET_LS** data type when the underlying object is released by the database engine as a result of direct or indirect action by the application. In the implicit case, a runtime callback is issued to the application so that it can clean up the context handle. For more information on implicitly disassociating from the **JET_LS** data type, see [JetSetLS](gg269243\(v=exchg.10\).md).

The following flags are associated with the JET_LS data type.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Term</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>JET_bitLSReset</p></td>
<td><p>The context handle is disassociated from the object.</p></td>
</tr>
<tr class="even">
<td><p>JET_bitLSCursor</p></td>
<td><p>Set or retrieve the local storage associated with a table cursor.</p></td>
</tr>
<tr class="odd">
<td><p>JET_bitLSTable</p></td>
<td><p>Set or retrieve the local storage associated with a table.</p></td>
</tr>
<tr class="even">
<td><p>JET_LSNil</p></td>
<td><p>The context handle is invalid.</p></td>
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
</tbody>
</table>


### See Also

[JetSetLS](gg269243\(v=exchg.10\).md)  
[JetGetLS](gg269234\(v=exchg.10\).md)

