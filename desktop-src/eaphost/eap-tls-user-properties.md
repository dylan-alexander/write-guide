---
title: EAP-TLS User Properties
description: Is an instance of the eaptlsuserpropertiesv1 legacy schema.
ms.assetid: d5a265a9-4c09-4a60-a188-dff471ee72c9
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# EAP-TLS User Properties

This sample is an instance of the [eaptlsuserpropertiesv1](eaptlsuserpropertiesv1schema-schema.md) legacy schema.

``` syntax
 <?xml version="1.0" ?> 
 <EapHostUserCredentials xmlns="http://www.microsoft.com/provisioning/EapHostUserCredentials" 
   xmlns:eapCommon="http://www.microsoft.com/provisioning/EapCommon" 
   xmlns:baseEap="http://www.microsoft.com/provisioning/BaseEapMethodUserCredentials"> 
   <EapMethod>
     <eapCommon:Type>13</eapCommon:Type> 
     <eapCommon:AuthorId>0</eapCommon:AuthorId> 
   </EapMethod>
   <Credentials xmlns:eapUser="http://www.microsoft.com/provisioning/EapUserPropertiesV1" 
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
     xmlns:baseEap="http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1" 
     xmlns:eapTls="http://www.microsoft.com/provisioning/EapTlsUserPropertiesV1">
     <baseEap:Eap>
       <baseEap:Type>13</baseEap:Type> 
       <eapTls:EapType>
         <eapTls:Username>ias-domain\test</eapTls:Username> 
         <eapTls:UserCert /> 
       </eapTls:EapType>
     </baseEap:Eap>
   </Credentials>
 </EapHostUserCredentials>
```

## Related topics

<dl> <dt>

[User Properties](user-profiles.md)
</dt> <dt>

[EAPHost and Legacy Schema](eaphost-schemas.md)
</dt> </dl>

 

 




