---
Description: IMSI
MS-HAID: WWAN\_profile\_v4.element\_IMSI
MSHAttr:
- PreferredSiteName:MSDN
- PreferredLib:/library/windows/desktop
title: IMSI
ms.topic: article
ms.date: 05/31/2018
---

# <span id="WWAN_profile_v4.element_IMSI"></span>IMSI

Specifies that this profile is active only when the current IMSI being used in the ICCID is the one specified. Otherwise, the profile is not applicable, and cannot be used to activate a Packet Data Protocol (PDP) context.

## Element hierarchy

[<MBNProfileExt>](element-mbnprofileext.md)  
[<ProfileConditionedOn>](element-profileconditionedon.md)  
**<IMSI>**

## Syntax

``` syntax
<IMSI>

  subscriberIdType

</IMSI>
```

## <span id="Attributes_and_Elements"></span><span id="attributes_and_elements"></span><span id="ATTRIBUTES_AND_ELEMENTS"></span>Attributes and Elements

### <span id="attributes"></span><span id="ATTRIBUTES"></span>Attributes

None.

### <span id="Child_Elements"></span><span id="child_elements"></span><span id="CHILD_ELEMENTS"></span>Child Elements

None.

### <span id="parent_elements"></span><span id="PARENT_ELEMENTS"></span>Parent Elements

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parent Element</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="element-profileconditionedon">ProfileConditionedOn</a></td>
<td><p>Specifies the conditions which must be satisfied for a profile to be applicable.</p>
<p>This element is new for v4. It enables you to specify multiple profiles that apply in different conditions, and for the proper profile to be used automatically when it is applicable. This element is optional. If you do not specify it, then the profile is always applicable with respect to the conditions listed.</p></td>
</tr>
</tbody>
</table>

 

## Requirements

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Namespace</p></td>
<td><p>https://www.microsoft.com/networking/WWAN/profile/v4</p></td>
</tr>
</tbody>
</table>

 

 



