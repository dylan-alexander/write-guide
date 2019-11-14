﻿---
title: JET_ERRINFOBASIC_W Structure
TOCTitle: JET_ERRINFOBASIC_W Structure
ms:assetid: fcc55cb7-718d-419a-a473-15e030c23abd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh475861(v=EXCHG.10)
ms:contentKeyID: 37033567
ms.date: 04/11/2016
ms.topic: article
---

# JET_ERRINFOBASIC_W Structure


_**Applies to:** Windows | Windows Server_

## JET_ERRINFOBASIC_W Structure

The **JET_ERRINFOBASIC_W** structure defines the data that is returned from the [JetGetErrorInfo()](hh475859\(v=exchg.10\).md) method when the JET_ErrorInfoSpecificErr InfoLevel is passed in.

Note: This documentation is based on a preliminary release of the Extensible Storage Engine. This information is subject to change.

    typedef struct { 
        unsigned long cbStruct; 
        JET_ERR errValue; 
        JET_ERRCAT errcatMostSpecific; 
        unsigned char rgCategoricalHierarchy[8]; 
        unsigned long lSourceLine; 
        WCHAR rgszSourceFile[64]; 
    } JET_ERRINFOBASIC_W;

### Members

**cbStruct**

The size of the structure, in bytes. It must be set to sizeof( JET_ERRINFOBASIC ).

**errValue**

The error value that was evaluated, as passed in for the *pvResult* argument to [JetGetErrorInfo()](hh475859\(v=exchg.10\).md).

**errcatMostSpecific**

The lowest-level [JET_ERRCAT](hh475860\(v=exchg.10\).md) constant that is associated with the error; that is, the leaf-level category in the category hierarchy documented in [JET_ERRCAT](hh475860\(v=exchg.10\).md).

**rgCategoricalHierarchy\[8\]**

The hierarchy of error categories that is associated with the error. Position 0 is the highest level in the hierarchy of [JET_ERRCAT](hh475860\(v=exchg.10\).md), and the rest are subcategories until the most specific category is set, after which all categories are JET_errcatUnknown.

**lSourceLine**

Reserved.

**rgszSourceFile\[64\]**

Reserved.

### Requirements

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Client</strong></p></td>
<td><p>Requires Windows 8.</p></td>
</tr>
<tr class="even">
<td><p><strong>Server</strong></p></td>
<td><p>Requires Windows 8 Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Header</strong></p></td>
<td><p>Declared in Esent.h.</p></td>
</tr>
</tbody>
</table>

