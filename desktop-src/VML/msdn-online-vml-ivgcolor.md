---
title: VML IVgColor
description: VML IVgColor
ms.assetid: 6121c5bf-1969-4402-9f45-8891a1538fea
ms.topic: article
ms.date: 05/31/2018
---

# VML IVgColor

This topic describes VML, a feature that is deprecated as of Windows Internet Explorer 9. Webpages and applications that rely on VML should be [migrated to SVG](https://go.microsoft.com/fwlink/p/?LinkID=236964) or other widely supported standards.

> [!Note]  
> As of December 2011, this topic has been archived. As a result, it is no longer actively maintained. For more information, see [Archived Content](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/). For information, recommendations, and guidance regarding the current version of Windows Internet Explorer, see [Internet Explorer Developer Center](https://go.microsoft.com/fwlink/p/?linkid=204313).

 

Specifies a color.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attributes</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>String</td>
<td>String. Text representation of the color. The following named color types are supported:
<ul>
<li>Black (#000000)</li>
<li>Silver (#C0C0C0)</li>
<li>Gray (#808080)</li>
<li>White (#FFFFFF)</li>
<li>Maroon (#800000)</li>
<li>Red (#FF0000)</li>
<li>Purple (#800080)</li>
<li>Fuchsia (#FF00FF)</li>
<li>Green (#008000)</li>
<li>Lime (#00FF00)</li>
<li>Olive (#808000)</li>
<li>Yellow (#FFFF00)</li>
<li>Navy (#000080)</li>
<li>Blue (#0000FF)</li>
<li>Teal (#008080)</li>
<li>Aqua (#00FFFF)</li>
</ul></td>
</tr>
<tr class="even">
<td>Type</td>
<td>VgColorType. Type of color. One of the following types:
<ul>
<li>Mixed</li>
<li>RGB</li>
<li>Scheme</li>
<li>Named</li>
</ul></td>
</tr>
<tr class="odd">
<td>RGB</td>
<td>VgRGBType. RGB value (<strong>Long</strong>) of the color. Only valid if Type is &quot;<strong>RGB</strong>&quot;.</td>
</tr>
<tr class="even">
<td>R</td>
<td><strong>Integer</strong>. Red component of the color. Can range between 0 and 255.</td>
</tr>
<tr class="odd">
<td>G</td>
<td><strong>Integer</strong>. Green component of the color. Can range between 0 and 255.</td>
</tr>
<tr class="even">
<td>B</td>
<td><strong>Integer</strong>. Blue component of the color. Can range between 0 and 255.</td>
</tr>
</tbody>
</table>



 

 

 




