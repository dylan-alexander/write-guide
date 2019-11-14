---
Description: The flags in the following table specify the status of an Output Protection Manager (OPM) session.
ms.assetid: d6d85fd4-e735-4610-93e0-bb2b1782f11b
title: OPM Status Flags (Opmapi.h)
ms.topic: reference
ms.date: 05/31/2018
---

# OPM Status Flags

The flags in the following table specify the status of an Output Protection Manager (OPM) session.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th style="text-align: left;">Constant/value</th>
<th style="text-align: left;">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;"><span id="OPM_STATUS_NORMAL"></span><span id="opm_status_normal"></span><dl> <dt><strong>OPM_STATUS_NORMAL</strong></dt> <dt>0x00</dt> </dl></td>
<td style="text-align: left;">Normal status.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><span id="OPM_STATUS_LINK_LOST"></span><span id="opm_status_link_lost"></span><dl> <dt><strong>OPM_STATUS_LINK_LOST</strong></dt> <dt>0x01</dt> </dl></td>
<td style="text-align: left;">The integrity of the connection has been compromised. Examples of events that cause the driver to set this flag include:<br/>
<ul>
<li>The driver can no longer enforce the current protection level.</li>
<li>The driver detected an internal integrity error.</li>
<li>The connector between the computer and the display device was unplugged.</li>
</ul></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><span id="OPM_STATUS_RENEGOTIATION_REQUIRED"></span><span id="opm_status_renegotiation_required"></span><dl> <dt><strong>OPM_STATUS_RENEGOTIATION_REQUIRED</strong></dt> <dt>0x02</dt> </dl></td>
<td style="text-align: left;">The connection configuration has changed. For example, the user has changed the desktop display mode.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><span id="OPM_STATUS_TAMPERING_DETECTED"></span><span id="opm_status_tampering_detected"></span><dl> <dt><strong>OPM_STATUS_TAMPERING_DETECTED</strong></dt> <dt>0x04</dt> </dl></td>
<td style="text-align: left;">The graphics adapter or the driver has been tampered with.<br/> This flag is not used in <em>COPP emulation mode</em>. Instead, the video output will set the OPM_STATUS_LINK_LOST flag if it detects tampering.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><span id="OPM_STATUS_REVOKED_HDCP_DEVICE_ATTACHED"></span><span id="opm_status_revoked_hdcp_device_attached"></span><dl> <dt><strong>OPM_STATUS_REVOKED_HDCP_DEVICE_ATTACHED</strong></dt> <dt>0x08</dt> </dl></td>
<td style="text-align: left;">A revoked High-Bandwidth Digital Content Protection (HDCP) device is attached to the video output.<br/> This status flag can be returned from an <a href="opm-get-virtual-protection-level">OPM_GET_VIRTUAL_PROTECTION_LEVEL</a> or <a href="opm-get-actual-protection-level">OPM_GET_ACTUAL_PROTECTION_LEVEL</a> query. <br/> The revoked device might be attached directly to the video output, or indirectly through an HDCP repeater. A video output is required to detect this condition while HDCP is enabled, but not otherwise.<br/> This flag is not used in <em>COPP emulation mode</em>, because the video output does not detect revoked devices in that mode.<br/></td>
</tr>
</tbody>
</table>



## Remarks

Some of these constants are equivalent to values from the **COPP\_StatusFlags** enumeration used in Certified Output Protection Protocol (COPP).

## Requirements



|                                     |                                                                                     |
|-------------------------------------|-------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                      |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                |
| Header<br/>                   | <dl> <dt>Opmapi.h</dt> </dl> |



## See also

<dl> <dt>

[OPM Enumerations](opm-enumerations.md)
</dt> </dl>

 

 




