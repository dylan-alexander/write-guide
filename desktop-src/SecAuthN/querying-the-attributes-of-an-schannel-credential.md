---
Description: Provides Schannel-specific information about a credential.
ms.assetid: 0c357996-b85a-4231-b258-40b35ab83ae2
title: Querying the Attributes of an Schannel Credential
ms.topic: article
ms.date: 05/31/2018
---

# Querying the Attributes of an Schannel Credential

The [**QueryCredentialsAttributes**](/windows/desktop/api/Sspi/nf-sspi-querycredentialsattributesa) function provides Schannel-specific information about a credential. This information is originally specified when the credential is created. For more information, see [Obtaining Schannel Credentials](obtaining-schannel-credentials.md). The information reported by this function is valid for any connections ([*security contexts*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx)) created by using the specified credential.

 

 



