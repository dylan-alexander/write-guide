---
Description: This topic is not current. For the most current information, see the Print Schema Specification.
ms.assetid: cb00edc9-2c8a-446d-989b-a4429ee8f544
title: ParameterDef
ms.topic: article
ms.date: 05/31/2018
---

# ParameterDef

This topic is not current. For the most current information, see the [Print Schema Specification](https://go.microsoft.com/?linkid=7141496).

A ParameterDef element defines the valid characteristics of parameter input. The value is entered by means of a ParameterInit element.

## Element Tag

<ParameterDef>

## XML Attributes

The following table lists the XML attributes that may be pertain to this element.



| XML Attribute   | Details                                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| name<br/> | Defines a unique name for the parameter in the context of the current document. Duplicate ParameterDef name attributes render the PrintCapabilities document invalid.<br/> |



 

For more information, please see [XML Attributes](xml-attributes.md) section.

## Element Information

The following table lists the elements that may be parents of this element, the elements that may be children of this element, and any restrictions on the element itself.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Category</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Parent elements<br/></td>
<td>PrintCapabilities <br/></td>
</tr>
<tr class="even">
<td>Child elements<br/></td>
<td>Property (one or more)<br/> The following standard Property elements must appear as the content of a ParameterDef element. <br/>
<ul>
<li>DataType <br/></li>
<li>DefaultValue <br/></li>
<li>Mandatory <br/></li>
<li>MaxLength or MaxValue<br/></li>
<li>MinLength or MinValue<br/></li>
<li>Multiple* <br/></li>
<li>UnitType <br/></li>
</ul></td>
</tr>
<tr class="odd">
<td>This element<br/></td>
<td>No character data is permitted.<br/> Duplicate child siblings are not permitted.<br/></td>
</tr>
</tbody>
</table>



 

\*Required when DataType is integer or decimal. Optional when DataType is string.

## Configuration Dependencies

A ParameterDef and its content to any nesting level may not have any configuration dependencies.

## Example

The following example sets all of the required Property elements for this parameter. The example in [ParameterInit](parameterinit.md) demonstrates how to initialize this parameter.

``` syntax
<psf:ParameterDef name="psk:PageMediaSizeMediaSizeHeight">
  <psf:Property name="psf:DataType">
    <psf:Value xsi:type="xs:string">xs:integer</psf:Value>
  </psf:Property>
  <psf:Property name="psf:UnitType">
    <psf:Value xsi:type="xs:string">microns</psf:Value>
  </psf:Property>
  <psf:Property name="psf:Multiple">
    <psf:Value xsi:type="xs:integer">1</psf:Value>
  </psf:Property>
  <psf:Property name="psf:MaxValue">
    <psf:Value xsi:type="xs:integer">594106</psf:Value>
  </psf:Property>
  <psf:Property name="psf:MinValue">
    <psf:Value xsi:type="xs:integer">152400</psf:Value>
  </psf:Property>
  <psf:Property name="psf:DefaultValue">
    <psf:Value xsi:type="xs:integer">152400</psf:Value>
  </psf:Property>
  <psf:Property name="psf:Mandatory">
    <psf:Value xsi:type="xs:string">psk:Optional</psf:Value>
  </psf:Property>
</psf:ParameterDef>
```

## Related topics

<dl> <dt>

[Print Schema Specification](https://go.microsoft.com/?linkid=7141496)
</dt> </dl>

 

 




