---
Description: Explains the procedure used for storing a session key.
ms.assetid: 9ab7f747-9c69-40b5-af78-163f3ba315bf
title: Procedure for Storing a Session Key
ms.topic: article
ms.date: 05/31/2018
---

# Procedure for Storing a Session Key

> [!Note]  
> This section assumes that users possess a set of [*public/private key pairs*](https://msdn.microsoft.com/en-us/library/ms721603(v=VS.85).aspx). Instructions and an example for creating key pairs can be found in [Example C Program: Creating a Key Container and Generating Keys](example-c-program-creating-a-key-container-and-generating-keys.md).

 

**To store a session key**

1.  Create a simple [*key BLOB*](https://msdn.microsoft.com/en-us/library/ms721590(v=VS.85).aspx) by using the [**CryptExportKey**](/windows/desktop/api/Wincrypt/nf-wincrypt-cryptexportkey) function. This will transfer the session key from the CSP to an application's memory space. Specify that an exchange public key be used to sign the key BLOB.
2.  Store the signed key BLOB to disk. It is assumed that all disks are nonsecure.
3.  When the key is needed, read the key BLOB from disk.
4.  Import the key BLOB back into the CSP by using the [**CryptImportKey**](/windows/desktop/api/Wincrypt/nf-wincrypt-cryptimportkey) function.

For an example of creating a [*session key*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) and exporting that key to a [*simple key BLOB*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) that can be written to a disk file, see [Example C Program: Exporting a Session Key](example-c-program-exporting-a-session-key.md).

This procedure provides only minimal security. If the stored session key will be used to encrypt data at a later date, the preceding procedure does not provide adequate security.

To provide greater security, sign the key BLOB with an exchange private key before it is stored to disk. When the key BLOB is later read from disk, its signature can be validated to ensure that the key BLOB is intact.

If the key BLOB is not signed, anyone with access to the disk or other media where the key is stored can create a new session key.

The new session key can be encrypted with the original user's [*public key*](https://msdn.microsoft.com/en-us/library/ms721603(v=VS.85).aspx) [*exchange key*](https://msdn.microsoft.com/en-us/library/ms721575(v=VS.85).aspx), and this new key can be substituted for the original. If the user unknowingly used the substituted session key to encrypt files and messages, the individual who created the substitute key could easily decrypt them.

Digital signatures are discussed in detail in [Hashes and Digital Signatures](hashes-and-digital-signatures.md).

 

 



