---
Description: Represents a collection of OID objects.
ms.assetid: 2c4ff87a-58e1-46aa-9680-29062b05308c
title: OIDs object
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- OIDs
api_type:
- COM
api_location:
- Capicom.dll
---

# OIDs object

\[The **OIDs** object is available for use in the operating systems specified in the Requirements section. Instead, use the [**OidCollection Class**](https://msdn.microsoft.com/library/023e15dk(v=VS.100).aspx) in the [**System.Security.Cryptography**](https://msdn.microsoft.com/library/9eat8fht(v=VS.100).aspx) namespace.\]

The **OIDs** object represents a collection of [**OID**](oid.md) objects. Each [**OID**](oid.md) object represents a single object identifier.

## When to use

The **OIDs** object is used to perform the following tasks:

-   Add or remove an [**OID**](oid.md) object from the collection.
-   Clear all the [**OID**](oid.md) objects from the collection.
-   Retrieve the number of object identifiers in the collection.
-   Retrieve a specific [**OID**](oid.md) object from the collection.
-   Iterate through the collection.

## Members

The **OIDs** object has these types of members:

-   [Methods](#methods)
-   [Properties](#properties)

### Methods

The **OIDs** object has these methods.



| Method                        | Description                                                                  |
|:------------------------------|:-----------------------------------------------------------------------------|
| [**Add**](oids-add.md)       | Adds an [**OID**](oid.md) object to the collection.<br/>              |
| [**Clear**](oids-clear.md)   | Clears all [**OID**](oid.md) objects from the collection.<br/>        |
| [**Remove**](oids-remove.md) | Removes an indexed [**OID**](oid.md) object from the collection.<br/> |



 

### Properties

The **OIDs** object has these properties.



| Property                                     | Access type          | Description                                                                                                                                                                                                                     |
|:---------------------------------------------|:---------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**\_NewEnum**](oids-newenum.md)<br/> | Read-only<br/> | Retrieves an [**IEnumVARIANT**](https://msdn.microsoft.com/en-us/library/ms221053(v=VS.71).aspx) interface on an object that can be used to enumerate the collection. This property is hidden within Visual Basic Scripting Edition (VBScript).<br/> |
| [**Count**](oids-count.md)<br/>       | Read-only<br/> | Retrieves the number of [**OID**](oid.md) objects in the collection.<br/>                                                                                                                                                |
| [**Item**](oids-item.md)<br/>         | Read-only<br/> | Retrieves an indexed [**OID**](oid.md) object from the collection. This is the default property.<br/>                                                                                                                    |



 

## Remarks

The **OIDs** object cannot be created.

The **OIDs** object is used by the following properties:

-   [**CertificateStatus.ApplicationPolicies**](certificatestatus-applicationpolicies.md)
-   [**CertificateStatus.CertificatePolicies**](certificatestatus-certificatepolicies.md)

## Requirements



|                            |                                                                                        |
|----------------------------|----------------------------------------------------------------------------------------|
| Redistributable<br/> | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>             | <dl> <dt>Capicom.dll</dt> </dl> |



 

 




