---
Description: The schannel SSP implements versions of the TLS, DTLS and SSL protocols. Different Windows versions support different protocol versions.
ms.assetid: FF716A4E-ABF2-4773-9588-9D200945A866
title: Protocols in TLS/SSL (Schannel SSP)
ms.topic: article
ms.date: 05/31/2018
---

# Protocols in TLS/SSL (Schannel SSP)

The schannel SSP implements versions of the TLS, DTLS and SSL protocols. Different Windows versions support different protocol versions.

The following table displays the Microsoft Schannel Provider support of TLS protocol versions:



| Windows OS                                            | TLS 1.0 Client | TLS 1.0 Server | TLS 1.1 Client | TLS 1.1 Server | TLS 1.2 Client | TLS 1.2 Server |
|-------------------------------------------------------|----------------|----------------|----------------|----------------|----------------|----------------|
| Windows Vista/Windows Server 2008                     | Enabled        | Enabled        | Not supported  | Not supported  | Not supported  | Not supported  |
| Windows Server 2008 with Service Pack 2 (SP2)         | Enabled        | Enabled        | Disabled       | Disabled       | Disabled       | Disabled       |
| Windows 7/Windows Server 2008 R2                      | Enabled        | Enabled        | Disabled       | Disabled       | Disabled       | Disabled       |
| Windows 8/Windows Server 2012                         | Enabled        | Enabled        | Enabled        | Enabled        | Enabled        | Enabled        |
| Windows 8.1/Windows Server 2012 R2                    | Enabled        | Enabled        | Enabled        | Enabled        | Enabled        | Enabled        |
| Windows 10, version 1507                              | Enabled        | Enabled        | Enabled        | Enabled        | Enabled        | Enabled        |
| Windows 10, version 1511                              | Enabled        | Enabled        | Enabled        | Enabled        | Enabled        | Enabled        |
| Windows 10, version 1607/Windows Server 2016 Standard | Enabled        | Enabled        | Enabled        | Enabled        | Enabled        | Enabled        |
| Windows 10, version 1703                              | Enabled        | Enabled        | Enabled        | Enabled        | Enabled        | Enabled        |



 

The following lists the Microsoft Schannel Provider support of DTLS protocol versions:



| Windows OS                                            | DTLS 1.0 Client | DTLS 1.0 Server | DTLS 1.2 Client | DTLS 1.2 Server |
|-------------------------------------------------------|-----------------|-----------------|-----------------|-----------------|
| Windows Vista/Windows Server 2008                     | Not supported   | Not supported   | Not supported   | Not supported   |
| Windows Server 2008 with SP2                          | Not supported   | Not supported   | Not supported   | Not supported   |
| Windows 7/Windows Server 2008 R2                      | Enabled         | Enabled         | Not supported   | Not supported   |
| Windows 8/Windows Server 2012                         | Enabled         | Enabled         | Not supported   | Not supported   |
| Windows 8.1/Windows Server 2012 R2                    | Enabled         | Enabled         | Not supported   | Not supported   |
| Windows 10, version 1507                              | Enabled         | Enabled         | Not supported   | Not supported   |
| Windows 10, version 1511                              | Enabled         | Enabled         | Not supported   | Not supported   |
| Windows 10, version 1607/Windows Server 2016 Standard | Enabled         | Enabled         | Enabled         | Enabled         |
| Windows 10, version 1703                              | Enabled         | Enabled         | Enabled         | Enabled         |



 

The following lists the Microsoft Schannel Provider support of pre-TLS standard protocols:



| Windows OS                                            | PCT 1.0       | SSL2 Client   | SSL2 Server   | SSL3 Client | SSL3 Server |
|-------------------------------------------------------|---------------|---------------|---------------|-------------|-------------|
| Windows Vista/Windows Server 2008                     | Not supported | Disabled      | Enabled       | Enabled     | Enabled     |
| Windows Server 2008 with SP2                          | Not supported | Disabled      | Enabled       | Enabled     | Enabled     |
| Windows 7/Windows Server 2008 R2                      | Not supported | Disabled      | Enabled       | Enabled     | Enabled     |
| Windows 8/Windows Server 2012                         | Not supported | Disabled      | Disabled      | Enabled     | Enabled     |
| Windows 8.1/Windows Server 2012 R2                    | Not supported | Disabled      | Disabled      | Enabled     | Enabled     |
| Windows 10, version 1507                              | Not supported | Disabled      | Disabled      | Enabled     | Enabled     |
| Windows 10, version 1511                              | Not supported | Disabled      | Disabled      | Enabled     | Enabled     |
| Windows 10, version 1607/Windows Server 2016 Standard | Not supported | Not supported | Not supported | Disabled    | Disabled    |
| Windows 10, version 1703                              | Not supported | Not supported | Not supported | Disabled    | Disabled    |



 

Beginning with Windows 10, version 1607 and Windows Server 2016, SSL 2.0 has been removed and is no longer supported.

> [!Note]  
> Note: All versions of Windows will accept a unified format "ClientHello" message even when SSL version 2 is disabled or no longer supported.

 

 

 



