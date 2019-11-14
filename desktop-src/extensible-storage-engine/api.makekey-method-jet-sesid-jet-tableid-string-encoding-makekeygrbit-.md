---
title: Api.MakeKey method (JET_SESID, JET_TABLEID, String, Encoding, MakeKeyGrbit)
TOCTitle: MakeKey method (JET_SESID, JET_TABLEID, String, Encoding, MakeKeyGrbit)
ms:assetid: M:Microsoft.Isam.Esent.Interop.Api.MakeKey(Microsoft.Isam.Esent.Interop.JET_SESID,Microsoft.Isam.Esent.Interop.JET_TABLEID,System.String,System.Text.Encoding,Microsoft.Isam.Esent.Interop.MakeKeyGrbit)
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.isam.esent.interop.api.makekey(v=EXCHG.10)
ms:contentKeyID: 55100830
ms.date: 07/30/2014
ms.topic: reference
dev_langs:
- vb
- csharp
api_name: 
- Microsoft.Isam.Esent.Interop.Api.MakeKey
topic_type: 
- apiref
- kbSyntax
api_type: 
- Managed
api_location: 
- Microsoft.Isam.Esent.Interop.dll
ROBOTS: INDEX,FOLLOW

---

# Api.MakeKey method (JET_SESID, JET_TABLEID, String, Encoding, MakeKeyGrbit)

Constructs a search key that may then be used by [JetSeek(JET_SESID, JET_TABLEID, SeekGrbit)](dn334003\(v=exchg.10\).md) and [JetSetIndexRange(JET_SESID, JET_TABLEID, SetIndexRangeGrbit)](dn334024\(v=exchg.10\).md).

**Namespace:**  [Microsoft.Isam.Esent.Interop](hh596136\(v=exchg.10\).md)  
**Assembly:**  Microsoft.Isam.Esent.Interop (in Microsoft.Isam.Esent.Interop.dll)

## Syntax

``` vb
'Declaration
Public Shared Sub MakeKey ( _
    sesid As JET_SESID, _
    tableid As JET_TABLEID, _
    data As String, _
    encoding As Encoding, _
    grbit As MakeKeyGrbit _
)
'Usage
Dim sesid As JET_SESID
Dim tableid As JET_TABLEID
Dim data As String
Dim encoding As Encoding
Dim grbit As MakeKeyGrbitApi.MakeKey(sesid, tableid, data, _
    encoding, grbit)
```

``` csharp
public static void MakeKey(
    JET_SESID sesid,
    JET_TABLEID tableid,
    string data,
    Encoding encoding,
    MakeKeyGrbit grbit
)
```

#### Parameters

  - sesid  
    Type: [Microsoft.Isam.Esent.Interop.JET_SESID](hh596745\(v=exchg.10\).md)  
    
    The session to use.

<!-- end list -->

  - tableid  
    Type: [Microsoft.Isam.Esent.Interop.JET_TABLEID](hh566310\(v=exchg.10\).md)  
    
    The cursor to create the key on.

<!-- end list -->

  - data  
    Type: [System.String](https://docs.microsoft.com/dotnet/api/system.string?redirectedfrom=MSDN)  
    
    Column data for the current key column of the current index.

<!-- end list -->

  - encoding  
    Type: [System.Text.Encoding](https://docs.microsoft.com/dotnet/api/system.text.encoding?redirectedfrom=MSDN)  
    
    The encoding used to convert the string.

<!-- end list -->

  - grbit  
    Type: [Microsoft.Isam.Esent.Interop.MakeKeyGrbit](hh578182\(v=exchg.10\).md)  
    
    Key options.

## See also

#### Reference

[Api class](dn292211\(v=exchg.10\).md)

[Api members](dn292213\(v=exchg.10\).md)

[MakeKey overload](dn334039\(v=exchg.10\).md)

[Microsoft.Isam.Esent.Interop namespace](hh596136\(v=exchg.10\).md)

