---
Description: This topic is not current. For the most current information, see the Print Schema Specification.
ms.assetid: 26e9e7d6-7c01-4687-aa64-7aea867b4e58
title: JobHolePunch
ms.topic: article
ms.date: 05/31/2018
---

# JobHolePunch

This topic is not current. For the most current information, see the [Print Schema Specification](https://go.microsoft.com/?linkid=7141496).

Describes the hole punching characteristics of the output. All documents are punched together. The JobHolePunch and DocumentHolePunch keywords are mutually exclusive. Both should not be specified simultaneously in a PrintTicket or Print Capabilities document.

-   [Element Information](#element-information)
-   [Structural Content](#structural-content)
-   [Extensible Markup Language (XML) Content](#extensible-markup-language-xml-content)

## Element Information



| Name                       |                                                                                                                                                 |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Element Type <br/>   | Feature<br/>                                                                                                                              |
| Scoping Prefix <br/> | Job<br/>                                                                                                                                  |
| Notes <br/>          | Top, Bottom, Left, and Right are relative to the PageImageableSize, where TopLeft is denoted by the origin of the x-axis and y-axis.<br/> |



 

## Structural Content

The XML structure of this element is:

``` syntax
<psf:Feature name="psk:JobHolePunch">
  <psf:Property name="psf:SelectionType">
    <psf:Value xsi:type="xs:string">psk:PickOne</psf:Value>
  </psf:Property>
  <psf:Option name="psk:_OptionName_">
    <psf:Property name="psf:IdentityOption">
      <psf:Value xsi:type="xs:string">_IdentityOptionValue_</psf:Value>
    </psf:Property>
  </psf:Option>
</psf:Feature>      
```

## Structure Variables

The following table outlines the characteristics of the variables defined in the XML structure.



| Name                               | Data type         | Unit                  | Supported values                                                                                                                                                                      | Summary                                                                      |
|------------------------------------|-------------------|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| \_OptionName\_<br/>          | string<br/> | characters<br/> | Valid fully qualified name as defined by [Namespaces in XML](https://go.microsoft.com/fwlink/p/?linkid=200944). If no namespace is specified, default namespace is assumed.<br/> | The name of the option.<br/>                                           |
| \_IdentityOptionValue\_<br/> | string<br/> | n/a<br/>        | True, False.<br/>                                                                                                                                                               | Defines an Option which when selected would disable this feature.<br/> |



 

## Extensible Markup Language (XML) Content

The public Print Schema keywords are defined in the https://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords namespace. The public Extensible Markup Language (XML) content for this keyword is defined below:

``` syntax
<psf:Feature name="psk:JobHolePunch">
  <psf:Property name="psf:SelectionType">
    <psf:Value xsi:type="xs:string">psk:PickOne</psf:Value>
  </psf:Property>
  <!-- Specifies hole(s) along the bottom edge. -->
  <psf:Option name="psk:BottomEdge" />
  <!-- Specifies hole(s) along the left edge. -->
  <psf:Option name="psk:LeftEdge" />
  <!-- Specifies no hole punching. -->
  <psf:Option name="psk:None" />
  <!-- Specifies hole(s) along the right edge. -->
  <psf:Option name="psk:RightEdge" />
  <!-- Specifies hole(s) along the top edge. -->
  <psf:Option name="psk:TopEdge" />
</psf:Feature>    
```

## Related topics

<dl> <dt>

[Print Schema Specification](https://go.microsoft.com/?linkid=7141496)
</dt> </dl>

 

 




