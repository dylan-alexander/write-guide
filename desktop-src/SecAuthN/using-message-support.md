---
Description: Explains how to use SSPI message support.
ms.assetid: 14d4813e-413e-4ef9-85f0-96986c3c1eca
title: Using Message Support
ms.topic: article
ms.date: 05/31/2018
---

# Using Message Support

After a handshake has been completed and a secure connection has been established, an application can use the [**MakeSignature**](/windows/desktop/api/Sspi/nf-sspi-makesignature), [**EncryptMessage (General)**](https://msdn.microsoft.com/en-us/library/Aa375378(v=VS.85).aspx), [**VerifySignature**](/windows/desktop/api/Sspi/nf-sspi-verifysignature), and [**DecryptMessage (General)**](https://msdn.microsoft.com/en-us/library/Aa375211(v=VS.85).aspx) functions to exchange signed or encrypted application data with the remote computer.

Examples that use these functions after a [*security context*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) has been established are demonstrated in the following sections:

-   [Signing a Message](signing-a-message.md)
-   [Verifying a Message](verifying-a-message.md)
-   [Encrypting a Message](encrypting-a-message.md)
-   [Decrypting a Message](decrypting-a-message.md)

 

 



