---
title: Creating an External Referral
description: If an external crossRef object is created and a domain controller uses it to generate a referral, the crossRef object provides two important data elements in the following properties.
ms.assetid: 9805390c-9e8d-4afd-bffc-43abf6055413
ms.tgt_platform: multiple
keywords:
- external referrals Active Directory
- Active Directory examples Active Directory , creating an external referral
ms.topic: article
ms.date: 05/31/2018
---

# Creating an External Referral

If an external [**crossRef**](https://docs.microsoft.com/windows/desktop/ADSchema/c-crossref) object is created and a domain controller uses it to generate a referral, the **crossRef** object provides two important data elements in the following properties. For more information about situations where this can occur, see the previous section.



| Property                           | Description                                                                                                                                                         |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**dnsRoot**](https://docs.microsoft.com/windows/desktop/ADSchema/a-dnsroot) | Specifies the server or domain that can serve data from the naming context specified in [**nCName**](https://docs.microsoft.com/windows/desktop/ADSchema/a-ncname).                                           |
| [**nCName**](https://docs.microsoft.com/windows/desktop/ADSchema/a-ncname)   | Specifies the distinguished name for the domain, schema, or configuration container rooted at the server or domain specified by [**dnsRoot**](https://docs.microsoft.com/windows/desktop/ADSchema/a-dnsroot). |



 

For example, if the server with DNS address of serv1.northwest.Fabrikam.com serves the naming context rooted at CN=MyContainer,OU=MyDOM,O=Fabrikam, set the [**dnsRoot**](https://docs.microsoft.com/windows/desktop/ADSchema/a-dnsroot) to that server's DNS address and the [**nCName**](https://docs.microsoft.com/windows/desktop/ADSchema/a-ncname) to the distinguished name of the domain, schema, or configuration container.

For more information and a code example that shows how to create an external referral, see [Example Code for Creating an External crossRef Object](example-code-for-creating-an-external-crossref-object.md).

 

 




