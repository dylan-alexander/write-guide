---
Description: IsAdditionalPdpContextProfile
MS-HAID: WWAN\_profile\_v3.element\_IsAdditionalPdpContextProfile
MSHAttr:
- PreferredSiteName:MSDN
- PreferredLib:/library/windows/desktop
title: IsAdditionalPdpContextProfile
ms.topic: article
ms.date: 05/31/2018
---

# <span id="WWAN_profile_v3.element_IsAdditionalPdpContextProfile"></span>IsAdditionalPdpContextProfile

The **IsAdditionalPdpContextProfile** element contains a **boolean** that is **true** if this is an "additional PDP (Packet Data Protocol) context" profile and **false**, otherwise. Default is **false**.

An "additional PDP context" profile is a profile that does not get activated over the physical adapter default port, and setting this element to true ensures that this profile is not displayed inappropriately in the user interface.

Note that if this element is set to true, then the following must also be true.

-   The [**IsDefault**](https://msdn.microsoft.com/library/Dd323288(v=VS.85).aspx) element must be unspecified or set to **false** for the profile to be valid.
-   The [**ConnectionMode**](https://msdn.microsoft.com/library/Dd323278(v=VS.85).aspx) element must be unspecified or set to **manual** for the profile to be valid.

## Element hierarchy

**<IsAdditionalPdpContextProfile>**

## Syntax

``` syntax
<IsAdditionalPdpContextProfile>

  boolean

</IsAdditionalPdpContextProfile>
```

## <span id="Attributes_and_Elements"></span><span id="attributes_and_elements"></span><span id="ATTRIBUTES_AND_ELEMENTS"></span>Attributes and Elements

### <span id="attributes"></span><span id="ATTRIBUTES"></span>Attributes

None.

### <span id="Child_Elements"></span><span id="child_elements"></span><span id="CHILD_ELEMENTS"></span>Child Elements

None.

### <span id="parent_elements"></span><span id="PARENT_ELEMENTS"></span>Parent Elements

This outermost (document) element may not be contained by any other elements.

## Requirements

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Namespace</p></td>
<td><p>https://www.microsoft.com/networking/WWAN/profile/v3</p></td>
</tr>
</tbody>
</table>

 

 



