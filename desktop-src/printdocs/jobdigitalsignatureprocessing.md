---
Description: This topic is not current. For the most current information, see the Print Schema Specification.
ms.assetid: 0592f7a4-cace-41b0-91e3-2811f72aeb3e
title: JobDigitalSignatureProcessing
ms.topic: article
ms.date: 05/31/2018
---

# JobDigitalSignatureProcessing

This topic is not current. For the most current information, see the [Print Schema Specification](https://go.microsoft.com/?linkid=7141496).

Describes configuring the digital signature processing for the entire job. Applicable only to content that contains digital signatures.

-   [Element Information](#element-information)
-   [Structural Content](#structural-content)

## Element Information



| Name                       |                    |
|----------------------------|--------------------|
| Element Type <br/>   | Feature<br/> |
| Scoping Prefix <br/> | Job<br/>     |
| Notes <br/>          | None<br/>    |



 

## Structural Content

The XML structure of this element is:

``` syntax
<psf:Feature name="psk:JobDigitalSignatureProcessing">
  <psf:Property name="SelectionType">
    <psf:Value xsi:type="xs:string">PickOne</psf:Value>
  </psf:Property>
  <psf:Option name="psk:_OptionName_">
    <psf:Property name="psf:IdentityOption">
      <psf:Value xsi:type="xs:string">_IdentityOptionValue_</psf:Value>
    </psf:Property>
  </psf:Feature>
```

## Structure Variables

The following table outlines the characteristics of the variables defined in the XML structure.



| Name                               | Data type         | Unit                   | Supported values                                                                                                                                                                      | Summary                                                                      |
|------------------------------------|-------------------|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| \_OptionName\_<br/>          | string<br/> | characters <br/> | Valid fully qualified name as defined by [Namespaces in XML](https://go.microsoft.com/fwlink/p/?linkid=200944). If no namespace is specified, default namespace is assumed.<br/> | The name of the option<br/>                                            |
| \_IdentityOptionValue\_<br/> | string<br/> | n/a<br/>         | True, False<br/>                                                                                                                                                                | Defines an Option which when selected would disable this feature.<br/> |



 

## Extensible Markup Language (XML) Content

The public Print Schema keywords are defined in the https://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords namespace. The public Extensible Markup Language (XML) content for this keyword is defined below:

``` syntax
<psf:Feature name="psk:JobDigitalSignatureProcessing">
  <psf:Property name="SelectionType">
    <psf:Value xsi:type="xs:string">PickOne</psf:Value>
  </psf:Property>
  <!-- Print the job regardless of the validity of the digital signatures. Digital signatures MAY be ignored.  -->
  <psf:Option name="psk:PrintInvalidSignatures" />
  <!-- Print the job regardless of the validity of the digital signatures.  In the event an invalid signature is encountered, an error page should print at the end of the job.  Digital signatures MUST not be ignored. -->
  <psf:Option name="psk:PrintInvalidSignaturesWithErrorReport" />
  <!-- Print the job only if all digital signatures are valid.  Digital signatures MUST not be ignored. -->
  <psf:Option name="psk:PrintOnlyValidSignatures" />
</psf:Feature>
```

## Related topics

<dl> <dt>

[Print Schema Specification](https://go.microsoft.com/?linkid=7141496)
</dt> </dl>

 

 




