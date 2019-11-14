---
Description: Certificates have associated properties, such as a display name, description, and allowed uses, that can be viewed and edited.
ms.assetid: 23faaa03-af3e-4497-8607-4e34f8889368
title: Creating, Viewing, and Managing Certificates
ms.topic: article
ms.date: 05/31/2018
---

# Creating, Viewing, and Managing Certificates

[*Certificates*](https://msdn.microsoft.com/en-us/library/ms721572(v=VS.85).aspx) are read-only structures. The contents of a certificate can be viewed but cannot be modified. Information in the certificate itself includes the certificate's validity dates, issuer, subject, and the public key. However, certificates have associated properties, such as a display name, description, and allowed uses, that can be viewed and edited.

This section demonstrates creating test certificates, viewing certificates, and managing certificates and other security objects. The certificates and [*Software Publisher Certificates*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) (SPCs) that can be created with MakeCert are strictly for test purposes. A test [*root certificate*](https://msdn.microsoft.com/en-us/library/ms721604(v=VS.85).aspx) and a test root [*private key*](https://msdn.microsoft.com/en-us/library/ms721603(v=VS.85).aspx) are provided for testing purposes only. Independent software vendors must obtain a certificate from GTE, VeriSign, Inc., or other [*certification authority*](https://msdn.microsoft.com/en-us/library/ms721572(v=VS.85).aspx) (CA) to sign code that will be distributed to the public.

This section includes the following topics:

-   [Using MakeCert](using-makecert.md)
-   [Using Cert2SPC](using-cert2spc.md)
-   [Using CertMgr](using-certmgr.md)

 

 



