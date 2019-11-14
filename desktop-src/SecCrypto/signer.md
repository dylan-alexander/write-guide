---
Description: Establishes the signer of a SignedData or SignedCode object.
ms.assetid: 'fca6489c-56cf-472f-ac0f-73ba531fa212'
title: Signer object
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- Signer
api_type:
- COM
api_location:
- Capicom.dll
---

# Signer object

\[The **Signer** object is available for use in the operating systems specified in the Requirements section. Instead, use the [**CmsSigner Class**](https://msdn.microsoft.com/library/5x3db70t(v=VS.90).aspx) in the [**System.Security.Cryptography.Pkcs**](https://msdn.microsoft.com/library/6see7k14(v=VS.100).aspx) namespace.\]

The **Signer** object establishes the signer of a [**SignedData**](signeddata.md) or [**SignedCode**](signedcode.md) object. The [**Certificate**](certificate.md) of the **Signer** object must have an available private key that can be used to sign data.

## Members

The **Signer** object has these types of members:

-   [Methods](#methods)
-   [Properties](#properties)

### Methods

The **Signer** object has these methods.



| Method                      | Description                                                       |
|:----------------------------|:------------------------------------------------------------------|
| [**Load**](signer-load.md) | Loads a signing certificate from a specified PFX file.<br/> |



 

### Properties

The **Signer** object has these properties.



| Property                                                                     | Access type           | Description                                                                                                                                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------------|:----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**AuthenticatedAttributes**](signer-authenticatedattributes.md)<br/> | Read-only<br/>  | The collection of authenticated attributes.<br/>                                                                                                                                                                                                                                                                                      |
| [**Certificate**](signer-certificate.md)<br/>                         | Read/write<br/> | The [**Certificate**](certificate.md) object that represents the certificate of a signer of the data.<br/> When the value of this property is reset, directly or indirectly, the whole [*state*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) of the object is reset.<br/> This is the default property.<br/> |
| [**Chain**](signer-chain.md)<br/>                                     | Read-only<br/>  | The chain of the signer.<br/>                                                                                                                                                                                                                                                                                                         |
| [**Options**](signer-options.md)<br/>                                 | Read/write<br/> | Sets or retrieves the signer's certificate option.<br/>                                                                                                                                                                                                                                                                               |



 

## Remarks

The **Signer** object can be created, and it is safe for scripting. The ProgID for the **Signer** object is CAPICOM.Signer.2.

**CAPICOM 1.*x*:** The ProgID for the **Signer** object is CAPICOM.Signer.1.

## Requirements



|                            |                                                                                        |
|----------------------------|----------------------------------------------------------------------------------------|
| Redistributable<br/> | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>             | <dl> <dt>Capicom.dll</dt> </dl> |



## See also

<dl> <dt>

[**Cryptography Objects**](cryptography-objects.md)
</dt> </dl>

 

 




