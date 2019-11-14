---
Description: This topic is not current. For the most current information, see the Print Schema Specification.
ms.assetid: b091c250-66f2-47cc-a012-1526c0ed02c9
title: PageMediaSizePSOrientation
ms.topic: article
ms.date: 05/31/2018
---

# PageMediaSizePSOrientation

This topic is not current. For the most current information, see the [Print Schema Specification](https://go.microsoft.com/?linkid=7141496).

Specifies the orientation relative to the feed-orientation direction (Reference [PostScript Printer Description File Format Specification](https://go.microsoft.com/fwlink/p/?linkid=178075)).

-   [Element Information](#element-information)
-   [Structure Content](#structure-content)

## Element Information



| Name                       |                                                             |
|----------------------------|-------------------------------------------------------------|
| Element Type <br/>   | ParameterDef<br/>                                     |
| Scoping Prefix <br/> | Page<br/>                                             |
| Notes <br/>          | Linked to PageMediaSize element, CustomPS option<br/> |



 

## Structure Content

The XML structure of this element is:

``` syntax
<psf:ParameterDef name="psk:PageMediaSizePSOrientation">
  <psf:Property name="psf:DataType">
    <psf:Value xsi:type="xs:string">xs:integer</psf:Value>
  </psf:Property>
  <psf:Property name="psf:DefaultValue">
    <psf:Value xsi:type="xs:integer">0</psf:Value>
  </psf:Property>
  <psf:Property name="psf:MaxValue">
    <psf:Value xsi:type="xs:integer">3</psf:Value>
  </psf:Property>
  <psf:Property name="psf:MinValue">
    <psf:Value xsi:type="xs:integer">0</psf:Value>
  </psf:Property>
  <psf:Property name="psf:Multiple">
    <psf:Value xsi:type="xs:integer">1</psf:Value>
  </psf:Property>
  <psf:Property name="psf:Mandatory">
    <psf:Value xsi:type="xs:string">psk:Conditional</psf:Value>
  </psf:Property>
  <psf:Property name="psf:UnitType">
    <psf:Value xsi:type="xs:string">PageMediaSizeEnum</psf:Value>
  </psf:Property>
</psf:ParameterDef>
      
```

## Structure Properties

The following table outlines the characteristics of the variables defined in the XML structure.



| Property                | xsi:type           | Value                        |
|-------------------------|--------------------|------------------------------|
| DataType<br/>     | string<br/>  | xs:integer<br/>        |
| DefaultValue<br/> | integer<br/> | 0<br/>                 |
| MaxValue<br/>     | integer<br/> | 3<br/>                 |
| MinValue<br/>     | integer<br/> | 0<br/>                 |
| Mandatory<br/>    | string<br/>  | psk:Conditional<br/>   |
| Multiple<br/>     | integer<br/> | 1<br/>                 |
| UnitType<br/>     | string<br/>  | PageMediaSizeEnum<br/> |



 

## Related topics

<dl> <dt>

[PostScript Printer Description File Format Specification](https://go.microsoft.com/fwlink/p/?linkid=178075)
</dt> <dt>

[Print Schema Specification](https://go.microsoft.com/?linkid=7141496)
</dt> </dl>

 

 




