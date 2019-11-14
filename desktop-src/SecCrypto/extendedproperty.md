---
Description: Represents a Microsoft-extended property.
ms.assetid: 91375fd5-b3af-4ed4-961d-5cc1db1a14e3
title: ExtendedProperty object
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- ExtendedProperty
api_type: 
- COM
api_location: 
- Capicom.dll
---

# ExtendedProperty object

\[CAPICOM is a 32-bit only component that is available for use in the following operating systems: Windows Server 2008, Windows Vista, and Windows XP. Instead, use Platform Invocation Services (PInvoke) to call the Win32 API function [**CertGetCertificateContextProperty**](/windows/desktop/api/Wincrypt/nf-wincrypt-certgetcertificatecontextproperty) and obtain the properties. For information about PInvoke, see [Platform Invoke Tutorial](https://go.microsoft.com/fwlink/p/?linkid=119531). The [.NET and CryptoAPI via P/Invoke: Part 1](https://go.microsoft.com/fwlink/p/?linkid=119533) and [.NET and CryptoAPI via P/Invoke: Part 2](https://go.microsoft.com/fwlink/p/?linkid=119534) subsections of [Extending .NET Cryptography with CAPICOM and P/Invoke](https://go.microsoft.com/fwlink/p/?linkid=119532) may also be helpful.\]

The **ExtendedProperty** object represents a Microsoft-extended property.

## When to use

The **ExtendedProperty** object is used to perform the following tasks:

-   Set or retrieve the type of the extended property.
-   Set or retrieve the type of encoding used to encode the extended property.

## Members

The **ExtendedProperty** object has these types of members:

-   [Properties](#properties)

### Properties

The **ExtendedProperty** object has these properties.



| Property                                             | Access type           | Description                                                                                                                                                                    |
|:-----------------------------------------------------|:----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**PropID**](extendedproperty-propid.md)<br/> | Read/write<br/> | A value of the [**CAPICOM\_PROPID**](capicom-propid.md) enumeration that sets or retrieves the type of extended property.<br/> This is the default property.<br/> |
| [**Value**](extendedproperty-value.md)<br/>   | Read/write<br/> | A value of the [**CAPICOM\_ENCODING\_TYPE**](capicom-encoding-type.md) enumeration that sets or retrieves the extended property data.<br/>                              |



 

## Remarks

The **ExtendedProperty** object is used by the [**ExtendedProperties**](extendedproperties.md) collection.

The **ExtendedProperty** object can be created, and it is not safe for scripting. The ProgID for the **ExtendedProperty** object is CAPICOM.ExtendedProperty.1.

## Requirements



|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| End of client support<br/> | Windows Vista<br/>                                                               |
| End of server support<br/> | Windows Server 2008<br/>                                                         |
| Redistributable<br/>       | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>                   | <dl> <dt>Capicom.dll</dt> </dl> |



 

 




