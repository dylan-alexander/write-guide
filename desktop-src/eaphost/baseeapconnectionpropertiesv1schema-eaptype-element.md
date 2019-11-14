---
title: EapType Element
description: Captures method-specific configuration inside the Eap element.
ms.assetid: f953e150-64cf-41b2-937f-410799be4602
keywords:
- EapType element EAPHost
topic_type:
- apiref
api_name:
- EapType
api_type:
- Schema
ms.author: windowssdkdev
ms.topic: reference
ms.date: 05/31/2018
api_location: 
ROBOTS: INDEX,FOLLOW
---

# EapType Element

The **EapType** element captures method-specific configuration inside the Eap element.

``` syntax
<xs:element name="EapType"
    type="BaseEapTypeParameters"
 />
```

## Remarks

The **EapType** element is abstract; each method must define and use a derived element in the instance documents.

## Requirements



|                                     |                                                      |
|-------------------------------------|------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>       |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/> |



## See also

<dl> <dt>

[EAPHost and Legacy Schema](eaphost-schemas.md)
</dt> <dt>

[baseeapconnectionpropertiesv1 Schema](baseeapconnectionpropertiesv1schema-schema.md)
</dt> </dl>

 

 





