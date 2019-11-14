---
Description: The Microsoft Media Foundation.
ms.assetid: 4C397139-6553-4707-B737-7C31C5D423BA
title: MP3 Audio Encoder
ms.topic: reference
ms.date: 05/31/2018
---

# MP3 Audio Encoder

The Microsoft Media Foundation MP3 audio encoder is a [Media Foundation Transform](media-foundation-transforms.md) (MFT) that encodes MPEG-1 layer 3 (MP3) audio.

## Class Identifier

The class identifier (CLSID) of the MP3 encoder is **CLSID\_MP3ACMCodecWrapper**, defined in the header file wmcodecdsp.h.

## Media Types

The MP3 encoder supports the following media types. The output type must be set before the input type.

### Output Types

Set the following attributes on the output media type.



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
<th>Remarks</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="mf-mt-major-type-attribute"><strong>MF_MT_MAJOR_TYPE</strong></a></td>
<td>Major type.</td>
<td>Must be <strong>MFMediaType_Audio</strong>.</td>
</tr>
<tr class="even">
<td><a href="mf-mt-subtype-attribute"><strong>MF_MT_SUBTYPE</strong></a></td>
<td>Audio subtype.</td>
<td>Must be <strong>MFAudioFormat_MP3</strong>.</td>
</tr>
<tr class="odd">
<td><a href="mf-mt-audio-avg-bytes-per-second-attribute"><strong>MF_MT_AUDIO_AVG_BYTES_PER_SECOND</strong></a></td>
<td>Bit rate of the encoded MP3 stream, in bytes per second.</td>
<td>The encoder supports all bit rates defined by the standard (32, 40, 48, 56, 64, 80, 96, 112, 128, 160, 192, 224, 256, or 320 Kbps).<br/> The default bit rates are 128 Kbps for mono and 320 Kbps for stereo.<br/> Use this attribute to specify the encoded bit rate.<br/></td>
</tr>
<tr class="even">
<td><a href="mf-mt-audio-num-channels-attribute"><strong>MF_MT_AUDIO_NUM_CHANNELS</strong></a></td>
<td>Number of channels.</td>
<td>The following values are supported:
<ul>
<li>1 (mono)</li>
<li>2 (stereo)</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="mf-mt-audio-samples-per-second-attribute"><strong>MF_MT_AUDIO_SAMPLES_PER_SECOND</strong></a></td>
<td>Samples per second.</td>
<td>The following values are supported:
<ul>
<li>48000 (48 KHz)</li>
<li>44100 (44.1 KHz)</li>
<li>32000 (32 KHz)</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="mf-mt-user-data-attribute">MF_MT_USER_DATA</a></td>
<td>Additional codec data.</td>
<td>This attribute contains the 12 bytes of the <a href="https://docs.microsoft.com/windows/desktop/api/mmreg/ns-mmreg-mpeglayer3waveformat"><strong>MPEGLAYER3WAVEFORMAT</strong></a> structure that follow the <strong>wfx</strong> member of that structure.</td>
</tr>
</tbody>
</table>



 

Alternatively, you can fill in an [**MPEGLAYER3WAVEFORMAT**](https://msdn.microsoft.com/en-us/library/Dd390710(v=VS.85).aspx) structure and call [**MFInitMediaTypeFromWaveFormatEx**](/windows/desktop/api/mfapi/nf-mfapi-mfinitmediatypefromwaveformatex) to convert the structure to a Media Foundation media type.

### Input Types

Set the following attributes on the input media type.



| Attribute                                                                               | Description         | Remarks                         |
|-----------------------------------------------------------------------------------------|---------------------|---------------------------------|
| [**MF\_MT\_MAJOR\_TYPE**](mf-mt-major-type-attribute.md)                               | Major type.         | Must be **MFMediaType\_Audio**. |
| [**MF\_MT\_SUBTYPE**](mf-mt-subtype-attribute.md)                                      | Subtype.            | Must be **MFAudioFormat\_PCM**. |
| [**MF\_MT\_AUDIO\_BITS\_PER\_SAMPLE**](mf-mt-audio-bits-per-sample-attribute.md)       | Bits per sample.    | Must be 16.                     |
| [**MF\_MT\_AUDIO\_SAMPLES\_PER\_SECOND**](mf-mt-audio-samples-per-second-attribute.md) | Samples per second. | Must match the output type.     |
| [**MF\_MT\_AUDIO\_NUM\_CHANNELS**](mf-mt-audio-num-channels-attribute.md)              | Number of channels. | Must match the output type.     |



 

The encoder supports only 16-bit integer PCM input. It does not support 32-bit floating point input.

### Media Formats

The MPEG-1 and MPEG-2 standard defines 252 layer 3 audio formats. The MP3 encoder supports the standard with some exceptions, as well as some additional formats, as described below. Layer 3 is defined as:



|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| Channels                         | mono or stereo                                                |
| MPEG-1 sample rates in kHz       | 44.1, 48, 32                                                  |
| MPEG-1 encoded bit rates in kbps | 32, 40, 48, 56, 64, 80, 96, 112, 128, 160, 192, 224, 256, 320 |
| MPEG-2 sample rates in kHz       | 8, 11.025, 12, 16, 22.05, 24                                  |
| MPEG-2 encoded bit rates in kbps | 8, 16, 24, 32, 40, 48, 56, 64, 80, 96, 112, 144, 160          |



 

The MP3 encoder also supports the following formats.



| Sample Rate | Bit Rate     | Channel Number |
|-------------|--------------|----------------|
| 8000        | 18000, 20000 | 2              |
| 11025       | 18000, 20000 | 1 or 2         |
| 12000       | 18000, 20000 | 1 or 2         |
| 16000       | 18000, 20000 | 1              |
| 32000       | 144000       | 1 or 2         |
| 44100       | 144000       | 1 or 2         |
| 48000       | 144000       | 1 or 2         |



 

The MP3 encoder does not support the following formats defined by the standard.



| Sample Rate | Bit Rates                                    | Channel Number |
|-------------|----------------------------------------------|----------------|
| 12000       | 80000, 96000, 112000, 128000, 144000, 160000 | 1 or 2         |
| 11025       | 80000, 96000, 112000, 128000, 144000, 160000 | 1 or 2         |
| 8000        | 80000, 96000, 112000, 128000, 144000, 160000 | 1 or 2         |
| 8000        | 8000, 11025, 12000, 16000, 22050, 24000      | 2              |



 

## Requirements



|                                     |                                                      |
|-------------------------------------|------------------------------------------------------|
| Minimum supported client<br/> | Windows 8 \[desktop apps only\]<br/>           |
| Minimum supported server<br/> | Windows Server 2012 \[desktop apps only\]<br/> |



## See also

<dl> <dt>

[Codec Objects](codecobjects.md)
</dt> </dl>

 

 




