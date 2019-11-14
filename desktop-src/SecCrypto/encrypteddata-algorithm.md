---
Description: Retrieves the algorithm for the encrypted data.
ms.assetid: 37bebe69-3c62-44c4-a5e5-c8cdbf087fa4
title: EncryptedData.Algorithm property
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- EncryptedData.Algorithm
api_type: 
- COM
api_location: 
- Capicom.dll
---

# EncryptedData.Algorithm property

\[CAPICOM is a 32-bit only component that is available for use in the following operating systems: Windows Server 2008, Windows Vista, and Windows XP. Instead, use Platform Invocation Services (PInvoke) to call the Win32 API functions [**CryptEncryptMessage**](/windows/desktop/api/Wincrypt/nf-wincrypt-cryptencryptmessage) and [**CryptDecryptMessage**](/windows/desktop/api/Wincrypt/nf-wincrypt-cryptdecryptmessage) to encrypt and decrypt messages. For information about PInvoke, see [Platform Invoke Tutorial](https://go.microsoft.com/fwlink/p/?linkid=119531). The [.NET and CryptoAPI via P/Invoke: Part 1](https://go.microsoft.com/fwlink/p/?linkid=119533) and [.NET and CryptoAPI via P/Invoke: Part 2](https://go.microsoft.com/fwlink/p/?linkid=119534) subsections of [Extending .NET Cryptography with CAPICOM and P/Invoke](https://go.microsoft.com/fwlink/p/?linkid=119532) may also be helpful.\]

The **Algorithm** property retrieves the algorithm for the encrypted data.

This property is read-only.

## Syntax


```VB
EncryptedData.Algorithm As Algorithm
```



## Property value

An [**Algorithm**](algorithm.md) object that represents the encryption algorithm.

## Requirements



|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| End of client support<br/> | Windows Vista<br/>                                                               |
| End of server support<br/> | Windows Server 2008<br/>                                                         |
| Redistributable<br/>       | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>                   | <dl> <dt>Capicom.dll</dt> </dl> |



## See also

<dl> <dt>

[**EncryptedData**](encrypteddata.md)
</dt> </dl>

 

 




