---
Description: Raised by a media stream when it starts or stops thinning the stream. For information about thinning, see About Rate Control.
ms.assetid: 7de8cb64-122a-475f-990c-c19590a9d9d8
title: MEStreamThinMode event (Mfobjects.h)
ms.topic: reference
ms.date: 05/31/2018
---

# MEStreamThinMode event

Raised by a media stream when it starts or stops thinning the stream. For information about *thinning*, see [About Rate Control](about-rate-control.md).

This event can be sent in response to the [**IMFRateControl::SetRate**](/windows/desktop/api/mfidl/nf-mfidl-imfratecontrol-setrate) method or the [**IMFQualityAdvise::SetDropMode**](/windows/desktop/api/mfidl/nf-mfidl-imfqualityadvise-setdropmode) method.

## Event values

Possible values retrieved from [**IMFMediaEvent::GetValue**](/windows/desktop/api/mfobjects/nf-mfobjects-imfmediaevent-getvalue) include the following.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>VARTYPE</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>VT_BOOL<br/></td>
<td>Indicates whether thinning has started or stopped.<br/>
<ul>
<li>VARIANT_TRUE: Samples delivered after this event are thinned.</li>
<li>VARIANT_FALSE: Samples delivered after this event are not thinned.</li>
</ul>
<br/></td>
</tr>
</tbody>
</table>



## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                                           |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Mfobjects.h (include Mfidl.h)</dt> </dl> |



## See also

<dl> <dt>

[Media Foundation Events](media-foundation-events.md)
</dt> </dl>

 

 




