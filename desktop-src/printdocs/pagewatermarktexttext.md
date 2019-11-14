---
Description: This topic is not current. For the most current information, see the Print Schema Specification.
ms.assetid: 3b01f05c-fe2e-4467-b2a7-5431a41200cd
title: PageWatermarkTextText
ms.topic: article
ms.date: 05/31/2018
---

# PageWatermarkTextText

This topic is not current. For the most current information, see the [Print Schema Specification](https://go.microsoft.com/?linkid=7141496).

Specifies the text of the watermark.

-   [Element Information](#element-information)
-   [Structure Content](#structure-content)

## Element Information



| Name                       |                                            |
|----------------------------|--------------------------------------------|
| Element Type <br/>   | ParameterDef<br/>                    |
| Scoping Prefix <br/> | Page<br/>                            |
| Notes <br/>          | Linked to PageWatermark element<br/> |



 

## Structure Content

The XML structure of this element is as follows:

``` syntax
<psf:ParameterDef name="psk:PageWatermarkTextText">
  <psf:Property name="psf:DataType">
    <psf:Value xsi:type="xs:string">xs:string</psf:Value>
  </psf:Property>
  <psf:Property name="psf:DefaultValue">
    <psf:Value xsi:type="xs:integer">_Undefined_</psf:Value>
  </psf:Property>
  <psf:Property name="psf:MaxLength">
    <psf:Value xsi:type="xs:integer">_Undefined_</psf:Value>
  </psf:Property>
  <psf:Property name="psf:MinLength">
    <psf:Value xsi:type="xs:integer">1</psf:Value>
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
| DataType<br/>     | String<br/>  | xs:string<br/>       |
| DefaultValue<br/> | Integer<br/> | undefined<br/>       |
| MaxLength<br/>    | Integer<br/> | undefined<br/>       |
| MinLength<br/>    | Integer<br/> | 1<br/>               |
| Mandatory<br/>    | String<br/>  | psk:Conditional<br/> |
| UnitType<br/>     | String<br/>  | characters<br/>      |



 

## Related topics

<dl> <dt>

[Print Schema Specification](https://go.microsoft.com/?linkid=7141496)
</dt> </dl>

 

 




