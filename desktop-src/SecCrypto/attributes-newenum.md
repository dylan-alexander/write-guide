---
Description: The \_NewEnum property of Attributes retrieves an IEnumVARIANT interface on an object that can be used to enumerate the collection. This property is hidden within Visual Basic Scripting Edition (VBScript).
ms.assetid: a90ef28b-3926-4542-bcd2-27f0eda4e339
title: Attributes._NewEnum property
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- Attributes._NewEnum
api_type:
- COM
api_location:
- Capicom.dll
---

# Attributes.\_NewEnum property

\[CAPICOM is a 32-bit only component that is available for use in the following operating systems: Windows Server 2008, Windows Vista, Windows XP. Instead, use the [**CryptographicAttributeObjectCollection Class**](https://msdn.microsoft.com/library/ms147988(v=VS.90).aspx) in the [**System.Security.Cryptography**](https://msdn.microsoft.com/library/9eat8fht(v=VS.100).aspx) namespace.\]

The **\_NewEnum** property retrieves an [**IEnumVARIANT**](https://msdn.microsoft.com/en-us/library/ms221053(v=VS.71).aspx) interface on an object that can be used to enumerate the collection. This property is hidden within Visual Basic Scripting Edition (VBScript).

## Syntax


```VB
Attributes._NewEnum As IUnknown
```



## Property value

An [**IEnumVARIANT**](https://msdn.microsoft.com/en-us/library/ms221053(v=VS.71).aspx) interface on an object that can be used to enumerate the collection.

## Remarks

This property is automatically used internally when you use the `For Each In` construct in Visual Basic Scripting Edition (VBScript).

## Requirements



|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| End of client support<br/> | Windows Vista<br/>                                                               |
| End of server support<br/> | Windows Server 2008<br/>                                                         |
| Redistributable<br/>       | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>                   | <dl> <dt>Capicom.dll</dt> </dl> |



## See also

<dl> <dt>

[**Attributes**](attributes.md)
</dt> </dl>

 

 




