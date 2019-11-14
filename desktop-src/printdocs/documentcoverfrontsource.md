---
Description: This topic is not current. For the most current information, see the Print Schema Specification.
ms.assetid: ec41d0c8-ea77-44ac-a02b-6a48237b324f
title: DocumentCoverFrontSource
ms.topic: article
ms.date: 05/31/2018
---

# DocumentCoverFrontSource

This topic is not current. For the most current information, see the [Print Schema Specification](https://go.microsoft.com/?linkid=7141496).

Specifies the source for a custom front-cover sheet.

-   [Element Information](#element-information)
-   [Structure Content](#structure-content)

## Element Information



| Name                       |                                                 |
|----------------------------|-------------------------------------------------|
| Element Type <br/>   | ParameterDef<br/>                         |
| Scoping Prefix <br/> | Document<br/>                             |
| Notes <br/>          | Linked to DocumentCoverFront element<br/> |



 

## Structure Content

The XML structure of this element is:

``` syntax
<psf:ParameterDef name="psk:DocumentCoverFrontSource">
  <psf:Property name="psf:DataType">
    <psf:Value xsi:type="xs:string">xs:string</psf:Value>
  </psf:Property>
  <psf:Property name="psf:DefaultValue">
    <psf:Value xsi:type="xs:string">_Undefined_</psf:Value>
  </psf:Property>
  <psf:Property name="psf:MaxLength">
    <psf:Value xsi:type="xs:integer ">_Undefined_</psf:Value>
  </psf:Property>
  <psf:Property name="psf:MinLength">
    <psf:Value xsi:type="xs:integer ">1</psf:Value>
  </psf:Property>
  <psf:Property name="psf:Mandatory">
    <psf:Value xsi:type="xs:string">psk:Conditional</psf:Value>
  </psf:Property>
  <psf:Property name="psf:UnitType">
    <psf:Value xsi:type="xs:string">characters</psf:Value>
  </psf:Property>
</psf:ParameterDef>      
```

## Structure Properties

The following table outlines the characteristics of the variables defined in the XML structure.



| Property                | xsi:type           | Value                      |
|-------------------------|--------------------|----------------------------|
| DataType<br/>     | string<br/>  | xs:string<br/>       |
| DefaultValue<br/> | string<br/>  | undefined<br/>       |
| MaxLength<br/>    | integer<br/> | undefined<br/>       |
| MinLength<br/>    | integer<br/> | 1<br/>               |
| Mandatory<br/>    | string<br/>  | psk:Conditional<br/> |
| UnitType<br/>     | string<br/>  | characters<br/>      |



 

## Related topics

<dl> <dt>

[Print Schema Specification](https://go.microsoft.com/?linkid=7141496)
</dt> </dl>

 

 




