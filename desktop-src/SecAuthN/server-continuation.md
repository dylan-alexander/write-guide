---
Description: Based on the return code from a previous call to AcceptSecurityContext (General), the server can wait for a response from the client and can participate in additional exchanges with the client.
ms.assetid: 281e1f81-3524-4034-bee5-cef6b13cf402
title: Server Continuation
ms.topic: article
ms.date: 05/31/2018
---

# Server Continuation

Based on the return code from a previous call to [**AcceptSecurityContext (General)**](https://msdn.microsoft.com/en-us/library/Aa374703(v=VS.85).aspx), the server can wait for a response from the client and can participate in additional exchanges with the client. To continue the authentication protocol, the server repeats calls to **AcceptSecurityContext (General)**.

The status returned by [**AcceptSecurityContext (General)**](https://msdn.microsoft.com/en-us/library/Aa374703(v=VS.85).aspx) is checked to see if the server needs to wait for additional messages from the client. In most authentication protocols, there is a maximum number of exchanges even for mutual authentication. Currently, both the NTLM and [*Kerberos protocols*](https://msdn.microsoft.com/en-us/library/ms721590(v=VS.85).aspx) do mutual authentication with three exchanges.

 

 



