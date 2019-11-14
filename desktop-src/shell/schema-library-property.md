---
Description: The <property> element specifies a property used by the library. These properties are specific to the library, so there is no predefined set of property names to use. This element is optional and has no child elements.
ms.assetid: 8BF6EC7A-A87E-45fe-A8F0-4B49594E9E7B
title: property Element (Library Schema)
ms.topic: article
ms.date: 05/31/2018
---

# property Element (Library Schema)

The <property> element specifies a property used by the library. These properties are specific to the library, so there is no predefined set of property names to use. This element is optional and has no child elements.

## Syntax

``` syntax
<!-- property -->
<xs:element name="property" minOccurs="0" maxOccurs="unbounded">
    <xs:complexType>
        <xs:complexContent>
            <xs:extension base="xs:anyType">
                <xs:attribute name="name" type="canonical-name" use="required"/>
                    <xs:simpleType name="canonical-name">
                        <xs:restriction base="xs:string">
                            <xs:maxLength value="63"/>
                            <xs:pattern value="[0-9A-Za-z.]*"/>
                        </xs:restriction>
                    </xs:simpleType>
                <xs:attribute name="type"/>
            </xs:extension>
        </xs:complexContent>
    </xs:complexType>
</xs:element>
```

## Element Information



| Parent Element                                                             | Child Elements |
|----------------------------------------------------------------------------|----------------|
| [propertyStore Element (Library Schema)](schema-library-propertystore.md) | None           |



 

## Attributes



<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribute</th>
<th>Description</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>name</td>
<td>Public. Required. The display name of the property.</td>

</tr>
<tr class="even">
<td>type</td>
<td>Public. Required. The type of property.</td>
<td><ul>
<li>Any: Default. The value will not be coerced by the property subsystem. VT_NULL will be returned by GetPropertyType.</li>
<li>Null: There is no value for this property. VT_NULL will be returned by GetPropertyType.</li>
<li>String: The value must be a VT_LPWSTR.</li>
<li>Boolean: The value must be a VT_BOOL.</li>
<li>Byte: The value must be a VT_UI1.</li>
<li>Buffer: The value must be a VT_UI1 | VT_VECTOR buffer of bytes.</li>
<li>Int16: The value must be a VT_I2.</li>
<li>UInt16: The value must be a VT_UI2.</li>
<li>Int32: The value must be a VT_I4.</li>
<li>UInt32: The value must be a VT_UI4.</li>
<li>Int64: The value must be a VT_I8.</li>
<li>UInt64: The value must be a VT_UI8.</li>
<li>Double: The value must be a VT_R8.</li>
<li>DateTime: The value must be a VT_FILETIME.</li>
<li>Guid: The value must be a VT_CLSID.</li>
<li>Blob: The value must be a VT_BLOB.</li>
<li>Object: The value must be a VT_UNKNOWN.</li>
<li>Stream: The value must be a VT_STREAM.</li>
<li>Clipboard: The value must be a VT_CF.</li>
</ul></td>
</tr>
</tbody>
</table>



 

## Remarks

The requirements for the <canonical-name> element match the requirements for Windows Search and the Windows property system. The string must be of type canonical-type.

## Related topics

<dl> <dt>

[Library Description Schema](library-schema-entry.md)
</dt> <dt>

[Property Schemas](https://msdn.microsoft.com/en-us/library/Cc144135(v=VS.85).aspx)
</dt> <dt>

[Search Connector Description Schema](https://msdn.microsoft.com/library/Dd940480(v=VS.85).aspx)
</dt> </dl>

 

 



