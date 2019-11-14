---
Description: This topic is not current. For the most current information, see the Print Schema Specification.
ms.assetid: c7abb657-6c9d-435a-a700-2eb0f14707c0
title: JobURI
ms.topic: article
ms.date: 05/31/2018
---

# JobURI

This topic is not current. For the most current information, see the [Print Schema Specification](https://go.microsoft.com/?linkid=7141496).

Specifies a uniform resource identifier (URI) for the document.

-   [Element Information](#element-information)
-   [Structural Content](#structural-content)
-   [Extensible Markup Language (XML) Content](#extensible-markup-language-xml-content)

## Element Information



| Name                       |                     |
|----------------------------|---------------------|
| Element Type <br/>   | Property<br/> |
| Scoping Prefix <br/> | Job<br/>      |
| Notes <br/>          | None<br/>     |



 

## Structural Content

The XML structure of this element is as follows:

``` syntax
<psf:Property name="psk:JobURI">
    <psf:Value xsi:type="xs:string">_JobURIValue_</psf:Value>
</psf:Property>
      
```

## Structure Variables

The following table outlines the characteristics of the variables defined in the XML structure.



| Name                       | Data type         | Unit | Supported values | Summary |
|----------------------------|-------------------|------|------------------|---------|
| \_JobURIValue\_<br/> | string<br/> |      |                  |         |



 

## Extensible Markup Language (XML) Content

``` syntax
<psf:Property name="psk:JobURI">
    <psf:Value xsi:type="xs:string"></psf:Value> <!-- undefined -->
</psf:Property>
```

## Related topics

<dl> <dt>

[Print Schema Specification](https://go.microsoft.com/?linkid=7141496)
</dt> </dl>

 

 




