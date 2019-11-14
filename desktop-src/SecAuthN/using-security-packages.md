---
Description: Lists the security packages that can be used with SSPI.
ms.assetid: f5999d41-b334-49be-8883-d9b9042d20dc
title: Using Security Packages
ms.topic: article
ms.date: 05/31/2018
---

# Using Security Packages

The [*Security Support Provider Interface*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) (SSPI) can be used with the following [*security packages*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx):

-   [Kerberos Security Package](#kerberos-security-package)
-   [NTLM Security Package](#ntlm-security-package)

The [*Kerberos*](https://msdn.microsoft.com/en-us/library/ms721590(v=VS.85).aspx) and NTLM protocols are implemented as security packages from the Secur32.dll [*security support provider*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) (SSP) supplied with the operating system. By default, support for both Kerberos and NTLM authentication are loaded by the [*local security authority*](https://msdn.microsoft.com/en-us/library/ms721592(v=VS.85).aspx) (LSA) on a computer when the system starts. In Windows Server or Windows domains, either package can be used to authenticate network logons and client/server connections. Which one is used depends on the capabilities of the computer on the other side of the connection. The Kerberos protocol is always preferred, if available.

After a security context for an interactive user has been established, another instance of the Kerberos or NTLM package can be loaded by a process running in the security context of the user to support the exchanging, signing, verifying, encrypting, and decrypting of messages. However, no process other than the LSA is ever permitted access to [*session keys*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) or tickets in the credentials cache.

System services and transport-level applications access an SSP through SSPI, which provides functions for enumerating the security packages available on a system, selecting a package, and using that package to obtain an authenticated connection.

The methods in SSPI are generic routines that developers can use without knowing the details of a particular [*security protocol*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx). For example, when a client/server connection is authenticated:

1.  The application on the client side of the connection sends [*credentials*](https://msdn.microsoft.com/en-us/library/ms721572(v=VS.85).aspx) to the server using the SSPI function [**InitializeSecurityContext (General)**](https://msdn.microsoft.com/en-us/library/Aa375506(v=VS.85).aspx).
2.  The application on the server side of the connection responds with the SSPI function [**AcceptSecurityContext (General)**](https://msdn.microsoft.com/en-us/library/Aa374703(v=VS.85).aspx).
3.  After the connection has been authenticated, the LSA on the server uses information from the client to build an [*access token*](https://msdn.microsoft.com/en-us/library/ms721532(v=VS.85).aspx).
4.  The server can then call the SSPI function [**ImpersonateSecurityContext**](/windows/desktop/api/Sspi/nf-sspi-impersonatesecuritycontext) to attach the access token to an impersonation thread for the service.

## Kerberos Security Package

The Kerberos [*security package*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) is based on the [*Kerberos authentication protocol*](https://msdn.microsoft.com/en-us/library/ms721590(v=VS.85).aspx).

If the Kerberos protocol is being used to authenticate a client/server connection, [**InitializeSecurityContext (Kerberos)**](https://msdn.microsoft.com/en-us/library/Aa375507(v=VS.85).aspx) generates a GSSAPI message that includes a KRB\_AP\_REQ message from the client. [**AcceptSecurityContext (Kerberos)**](https://msdn.microsoft.com/en-us/library/Aa374704(v=VS.85).aspx) then generates a GSSAPI message that includes a KRB\_AP\_REP message from the server.

For background information on the steps that take place behind the scenes in the implementation of a Kerberos protocol, see [Microsoft Kerberos](microsoft-kerberos.md).

All distributed services use SSPI to access the Kerberos protocol. A partial list of the ways in which the Kerberos protocol is used for authentication includes:

-   Print spooler services
-   CIFS/SMB remote file access
-   [*LDAP*](https://msdn.microsoft.com/en-us/library/ms721592(v=VS.85).aspx) queries to the Active Directory
-   Distributed file system management and referrals
-   IPsec host-to-host security authority authentication
-   Reservation requests for network Quality of Service
-   Intranet authentication to Internet Information Services
-   Remote server or workstation management using authenticated RPC
-   [*Certificate requests*](https://msdn.microsoft.com/en-us/library/ms721572(v=VS.85).aspx) to Certificate Services for domain users and computers

## NTLM Security Package

The NTLM security package is based on the NTLM authentication protocol.

 

 



