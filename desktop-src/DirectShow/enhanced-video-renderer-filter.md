---
Description: The Enhanced Video Renderer (EVR) filter is a 16-channel video mixer and renderer. It has the same core functionality and plug-in model as the Media Foundation EVR media sink.
ms.assetid: ead99cb3-2be2-42c6-ac22-be0c2ddf28d5
title: Enhanced Video Renderer Filter
ms.topic: reference
ms.date: 05/31/2018
---

# Enhanced Video Renderer Filter

> [!Note]  
> This topic applies to Windows Vista and later.

 

The Enhanced Video Renderer (EVR) filter is a 16-channel video mixer and renderer. It has the same core functionality and plug-in model as the Media Foundation EVR media sink.

The DirectShow EVR filter is documented in the Media Foundation SDK documentation; for more information, see [Enhanced Video Renderer](https://go.microsoft.com/fwlink/p/?linkid=104315).



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Filter Interfaces (through <strong>QueryInterface</strong>)</td>
<td>DirectShow interfaces:
<ul>
<li><a href="/windows/desktop/api/Strmif/nn-strmif-iamcertifiedoutputprotection"><strong>IAMCertifiedOutputProtection</strong></a></li>
<li><a href="/windows/desktop/api/Strmif/nn-strmif-iamfiltermiscflags"><strong>IAMFilterMiscFlags</strong></a></li>
<li><a href="/windows/desktop/api/Strmif/nn-strmif-ibasefilter"><strong>IBaseFilter</strong></a></li>
<li><a href="ikspropertyset"><strong>IKsPropertySet</strong></a></li>
<li><a href="/windows/desktop/api/Strmif/nn-strmif-imediaeventsink"><strong>IMediaEventSink</strong></a></li>
<li><a href="/windows/desktop/api/Strmif/nn-strmif-imediaseeking"><strong>IMediaSeeking</strong></a></li>
<li><a href="/windows/desktop/api/Strmif/nn-strmif-iqualitycontrol"><strong>IQualityControl</strong></a></li>
<li><a href="/windows/desktop/api/Amvideo/nn-amvideo-iqualprop"><strong>IQualProp</strong></a></li>
</ul>
Media Foundation interfaces:<br/>
<ul>
<li><a href="https://docs.microsoft.com/windows/desktop/api/evr/nn-evr-ievrfilterconfig"><strong>IEVRFilterConfig</strong></a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/api/mfidl/nn-mfidl-imfgetservice"><strong>IMFGetService</strong></a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/api/evr/nn-evr-imfvideopositionmapper"><strong>IMFVideoPositionMapper</strong></a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/api/evr/nn-evr-imfvideorenderer"><strong>IMFVideoRenderer</strong></a></li>
</ul></td>
</tr>
<tr class="even">
<td>Input Pin Media Types</td>
<td>Variable, depending on the graphics driver.</td>
</tr>
<tr class="odd">
<td>Input Pin Interfaces (through <strong>QueryInterface</strong>)</td>
<td>DirectShow interfaces:
<ul>
<li><a href="/windows/desktop/api/Strmif/nn-strmif-imeminputpin"><strong>IMemInputPin</strong></a></li>
<li><a href="/windows/desktop/api/Strmif/nn-strmif-ipin"><strong>IPin</strong></a></li>
<li><a href="/windows/desktop/api/Strmif/nn-strmif-iqualitycontrol"><strong>IQualityControl</strong></a></li>
</ul>
Media Foundation interfaces:<br/>
<ul>
<li><a href="https://docs.microsoft.com/windows/desktop/api/dxva2api/nn-dxva2api-idirectxvideomemoryconfiguration"><strong>IDirectXVideoMemoryConfiguration</strong></a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/api/evr9/nn-evr9-ievrvideostreamcontrol"><strong>IEVRVideoStreamControl</strong></a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/api/mfidl/nn-mfidl-imfgetservice"><strong>IMFGetService</strong></a></li>
</ul></td>
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
<td>CLSID_EnhancedVideoRenderer</td>
</tr>
<tr class="odd">
<td>Executable</td>
<td>evr.dll</td>
</tr>
<tr class="even">
<td><a href="merit">Merit</a></td>
<td>MERIT_DO_NOT_USE</td>
</tr>
<tr class="odd">
<td><a href="filter-categories">Filter Category</a></td>
<td>CLSID_LegacyAmFilterCategory</td>
</tr>
</tbody>
</table>



 

## Remarks

In addition to the interfaces exposed through **QueryInterface**, the EVR exposes other interfaces through the [**IMFGetService::GetService**](https://docs.microsoft.com/windows/desktop/api/mfidl/nf-mfidl-imfgetservice-getservice) method. Some of these interfaces are implemented by the EVR presenter or the EVR mixer, rather than the EVR itself. If the application sets a custom presenter or mixer on the EVR, the custom versions might expose a different set of interfaces.



| Object     | Service Identifier                                              | Interfaces                                                                                                                                                                                                                                                                                                     |
|------------|-----------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EVR filter | MR\_VIDEO\_RENDER\_SERVICE(Queries EVR or presenter)<br/> | [**IMFVideoDeviceID**](https://docs.microsoft.com/windows/desktop/api/evr/nn-evr-imfvideodeviceid)<br/> [**IMFVideoDisplayControl**](https://docs.microsoft.com/windows/desktop/api/evr/nn-evr-imfvideodisplaycontrol)<br/> [**IMFVideoPositionMapper**](https://docs.microsoft.com/windows/desktop/api/evr/nn-evr-imfvideopositionmapper)<br/> [**IMFVideoPresenter**](https://docs.microsoft.com/windows/desktop/api/evr/nn-evr-imfvideopresenter)<br/>                                                          |
| EVR filter | MR\_VIDEO\_ACCELERATION\_SERVICE(Queries presenter)<br/>  | [**IDirect3DDeviceManager9**](https://docs.microsoft.com/windows/desktop/api/dxva2api/nn-dxva2api-idirect3ddevicemanager9)                                                                                                                                                                                                                                                      |
| EVR filter | MR\_VIDEO\_MIXER\_SERVICE(Queries mixer)<br/>             | [**IMFVideoDeviceID**](https://docs.microsoft.com/windows/desktop/api/evr/nn-evr-imfvideodeviceid)<br/> [**IMFVideoMixerBitmap**](https://docs.microsoft.com/windows/desktop/api/evr9/nn-evr9-imfvideomixerbitmap)<br/> [**IMFVideoMixerControl**](https://docs.microsoft.com/windows/desktop/api/evr/nn-evr-imfvideomixercontrol)<br/> [**IMFVideoPositionMapper**](https://docs.microsoft.com/windows/desktop/api/evr/nn-evr-imfvideopositionmapper)<br/> [**IMFVideoProcessor**](https://docs.microsoft.com/windows/desktop/api/evr9/nn-evr9-imfvideoprocessor)<br/> |
| Input pins | MR\_VIDEO\_ACCELERATION\_SERVICE                                | [**IDirectXVideoMemoryConfiguration**](https://docs.microsoft.com/windows/desktop/api/dxva2api/nn-dxva2api-idirectxvideomemoryconfiguration)                                                                                                                                                                                                                                    |



 

The EVR can mix up to 16 video streams. The first input stream (pin 0) is called the *reference stream*. The reference stream always appears first in the z-order. Any additional streams are called substreams, and are mixed on top of the reference stream. The application can change the z-order of the substreams, but no substream can be first in the z-order.

The graphics driver determines which video formats are supported, but typically they are limited to the following:

-   Reference stream: Progressive or interlaced YUV with no per-pixel alpha (such as NV12 or YUY2); or progressive RGB.
-   Substreams: Progressive YUV with per-pixel-alpha, such as AYUV or AI44.

The available substream formats might depend on the format of the reference stream.

The EVR forwards seek commands upstream through pin 0. The substream pins do not forward seek commands. It is the responsibility of the source or splitter filter to keep the substreams synchronized with the reference stream.

## Requirements



|                                     |                                                      |
|-------------------------------------|------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>       |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/> |



## See also

<dl> <dt>

[DirectShow Filters](directshow-filters.md)
</dt> </dl>

 

 




