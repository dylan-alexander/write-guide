---
Description: DirectSound Renderer Filter
ms.assetid: ec6cc790-8c1f-4de4-a7ca-a7073894380e
title: DirectSound Renderer Filter
ms.topic: article
ms.date: 05/31/2018
---

# DirectSound Renderer Filter

This filter renders audio using DirectSound. This filter is currently the default audio renderer for waveform sound.

In addition to its basic sound-rendering capabilities, this filter can process DirectSound API calls. Use the [**IAMDirectSound**](/windows/desktop/api/Amaudio/nn-amaudio-iamdirectsound) methods to set and retrieve the window that will handle the sound playback. The DirectSound Audio Renderer is the default audio rendering filter for DirectShow.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Filter Interfaces</td>
<td><a href="/windows/desktop/api/Strmif/nn-strmif-iamaudiorendererstats"><strong>IAMAudioRendererStats</strong></a>, <a href="/windows/desktop/api/Strmif/nn-strmif-iamclockslave"><strong>IAMClockSlave</strong></a>, <a href="/windows/desktop/api/Amaudio/nn-amaudio-iamdirectsound"><strong>IAMDirectSound</strong></a>, <a href="/windows/desktop/api/Strmif/nn-strmif-iamresourcecontrol"><strong>IAMResourceControl</strong></a>, <a href="/windows/desktop/api/Strmif/nn-strmif-ibasefilter"><strong>IBaseFilter</strong></a>, <a href="/windows/desktop/api/Control/nn-control-ibasicaudio"><strong>IBasicAudio</strong></a>, <strong>IDirectSound3DBuffer</strong>, <strong>IDirectSound3dListener</strong>, <a href="/windows/desktop/api/Control/nn-control-imediaposition"><strong>IMediaPosition</strong></a>, <a href="/windows/desktop/api/Strmif/nn-strmif-imediaseeking"><strong>IMediaSeeking</strong></a>, <a href="/windows/desktop/api/Strmif/nn-strmif-iqualitycontrol"><strong>IQualityControl</strong></a>, <a href="/windows/desktop/api/Strmif/nn-strmif-ireferenceclock"><strong>IReferenceClock</strong></a></td>
</tr>
<tr class="even">
<td>Input Pin Media Types</td>
<td>Major Type: MEDIATYPE_AudioSubtypes:<br/>
<ul>
<li>MEDIASUBTYPE_PCM</li>
<li>MEDIASUBTYPE_IEEE_FLOAT</li>
<li>MEDIASUBTYPE_DOLBY_AC3_SPDIF</li>
<li>MEDIASUBTYPE_RAW_SPORT</li>
<li>MEDIASUBTYPE_SPDIF_TAG_241h</li>
<li>MEDIASUBTYPE_DRM_Audio</li>
</ul>
Format type: FORMAT_WaveFormatEx<br/></td>
</tr>
<tr class="odd">
<td>Input Pin Interfaces</td>
<td><a href="/windows/desktop/api/Strmif/nn-strmif-imeminputpin"><strong>IMemInputPin</strong></a>, <a href="/windows/desktop/api/Strmif/nn-strmif-ipin"><strong>IPin</strong></a>, <a href="/windows/desktop/api/Strmif/nn-strmif-ipinconnection"><strong>IPinConnection</strong></a>, <a href="/windows/desktop/api/Strmif/nn-strmif-iqualitycontrol"><strong>IQualityControl</strong></a></td>
</tr>
<tr class="even">
<td>Output Pin Media Types</td>
<td>Not applicable.</td>
</tr>
<tr class="odd">
<td>Output Pin Interfaces</td>
<td>Not applicable.</td>
</tr>
<tr class="even">
<td>Filter CLSID</td>
<td>CLSID_DSoundRender</td>
</tr>
<tr class="odd">
<td>Property Page CLSID</td>
<td>CLSID_AudioProperties, CLSID_AudioRendererAdvancedProperties</td>
</tr>
<tr class="even">
<td>Executable</td>
<td>quartz.dll</td>
</tr>
<tr class="odd">
<td><a href="merit">Merit</a></td>
<td>MERIT_PREFERRED</td>
</tr>
<tr class="even">
<td><a href="filter-categories">Filter Category</a></td>
<td>CLSID_AudioRendererCategory</td>
</tr>
</tbody>
</table>



 

## Remarks

This filter acts as a wrapper for an audio device. To enumerate the audio devices available on the user's system, use the [**ICreateDevEnum**](/windows/desktop/api/Strmif/nn-strmif-icreatedevenum) interface with the audio renderer category (CLSID\_AudioRendererCategory). For each audio device, the audio renderer category contains two filter instances. One of these corresponds to the DirectSound Renderer, and the other corresponds to the [Audio Renderer (WaveOut)](audio-renderer--waveout--filter.md) filter. The DirectSound instance has the friendly name "DirectSound: *DeviceName*," where *DeviceName* is the name of the device. The WaveOut instance has the friendly name *DeviceName*.

The audio renderer category contains two additional filter instances, named "Default DirectSound Device" and "Default WaveOut Device." These correspond to the default sound device, as chosen by the user through the Control Panel. They are actually mappings to one of the pairs described in the previous paragraph. For example, if the system has two audio devices, Device A and Device B, the audio renderer category will contain the following:

-   Device A
-   DirectSound: Device A
-   Device B
-   DirectSound: Device B
-   Default DirectSound Device
-   Default WaveOut Device

If the user selected Device A as the default device, then "Default DirectSound Device" is equivalent to "DirectSound: Device A," and "Default WaveOut Device" is equivalent to "Device A." If the user selects Device B as the default device, these mappings will change.

"Default DirectSound Device" is assigned a merit of MERIT\_PREFERRED. The others have merit MERIT\_DO\_NOT\_USE. Therefore, Intelligent Connect will always choose the default DirectSound device.

The DirectSound Renderer filter supports 3D sound through the DirectSound **IDirectSound3DBuffer** and **IDirectSound3dListener** interfaces. You can also query the filter for the current versions of these interfaces, **IDirectSound3DBuffer8** and **IDirectSound3dListener8**. Run the graph before calling methods on these interfaces.

## Related topics

<dl> <dt>

[DirectShow Filters](directshow-filters.md)
</dt> </dl>

 

 




