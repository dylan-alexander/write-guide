---
Description: Overlay Mixer 2 Filter
ms.assetid: 3d3871ac-518c-45a1-9e64-031f344f4527
title: Overlay Mixer 2 Filter
ms.topic: article
ms.date: 05/31/2018
---

# Overlay Mixer 2 Filter

The Overlay Mixer 2 filter is identical to the [Overlay Mixer](overlay-mixer-filter.md) filter, except:

-   It supports only media types with [**VIDEOINFOHEADER2**](/previous-versions/windows/desktop/api/dvdmedia/ns-dvdmedia-videoinfoheader2) formats.
-   It has a higher merit, which enables it to be added to a filter graph automatically.

The Overlay Mixer 2 is provided so that the Filter Graph Manager will add it to the graph when it renders non-DVD MPEG-2 video. The choice of whether to use the Overlay Mixer or the Overlay Mixer 2 is handled by the component that builds the graph, either the Filter Graph Manager, the Capture Graph Builder, or the DVD Graph Builder. From an application perspective, they are the same filter, with the same interfaces and functionality.

The following table contains information specific to the Overlay Mixer 2. For all other filter data, refer to the documentation for the Overlay Mixer.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Input Pin Media Types</td>
<td>Format Type: Format_VIDEOINFO2</td>
</tr>
<tr class="even">
<td>Filter CLSID</td>
<td>CLSID_OverlayMixer2</td>
</tr>
<tr class="odd">
<td><a href="merit">Merit</a></td>
<td><ul>
<li>MERIT_UNLIKELY</li>
<li>Windows Vista or later: MERIT_DO_NOT_USE</li>
</ul></td>
</tr>
</tbody>
</table>



 

In Windows Vista or later, the merit of the Overlay Mixer 2 filter is MERIT\_DO\_NOT\_USE, because the newer video renderers (VMR-7, VMR-9, and EVR) all support **VIDEOINFOHEADER2** formats, and therefore it is not necessary to use the Overlay Mixer.

## Related topics

<dl> <dt>

[DirectShow Filters](directshow-filters.md)
</dt> </dl>

 

 



