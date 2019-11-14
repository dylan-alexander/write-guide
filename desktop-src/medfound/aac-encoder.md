---
Description: The Microsoft Media Foundation AAC encoder is a Media Foundation Transform that encodes Advanced Audio Coding (AAC) Low Complexity (LC) profile, as defined by ISO/IEC 13818-7 (MPEG-2 Audio Part 7) .
ms.assetid: d88a8c32-c71f-4ddb-af8c-e2fb54c2322c
title: AAC Encoder
ms.topic: reference
ms.date: 05/31/2018
---

# AAC Encoder

The Microsoft Media Foundation AAC encoder is a [Media Foundation Transform](media-foundation-transforms.md) that encodes Advanced Audio Coding (AAC) Low Complexity (LC) profile, as defined by ISO/IEC 13818-7 (MPEG-2 Audio Part 7) .

The AAC encoder does not support encoding to any other AAC profiles, such as Main, SSR, or LTP.

## Class Identifier

The class identifier (CLSID) of the AAC encoder is **CLSID\_AACMFTEncoder**, defined in the header file wmcodecdsp.h.

## Media Types

The AAC encoder supports the following media types. You can set the types in either order input type first, or output type first.

### Input Types

Set the following attributes on the input media type.



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
<td>Subtype.</td>
<td>Must be <strong>MFAudioFormat_PCM</strong>.</td>
</tr>
<tr class="odd">
<td><a href="mf-mt-audio-bits-per-sample-attribute"><strong>MF_MT_AUDIO_BITS_PER_SAMPLE</strong></a></td>
<td>Bits per sample.</td>
<td>Must be 16.</td>
</tr>
<tr class="even">
<td><a href="mf-mt-audio-samples-per-second-attribute"><strong>MF_MT_AUDIO_SAMPLES_PER_SECOND</strong></a></td>
<td>Samples per second.</td>
<td>The following values are supported:
<ul>
<li>44100 (44.1 KHz)</li>
<li>48000 (48 KHz)</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="mf-mt-audio-num-channels-attribute"><strong>MF_MT_AUDIO_NUM_CHANNELS</strong></a></td>
<td>Number of channels.</td>
<td>Must be 1 (mono) or 2 (stereo), or 6 (5.1).
<blockquote>
[!Note]<br />
Support for 6 audio channels was introduced with Windows 10 and is not available for earlier versions of Windows.
</blockquote>
<br/></td>
</tr>
</tbody>
</table>



 

After the input type is set, the encoder derives the following values and adds them to the media type:

-   [**MF\_MT\_AUDIO\_AVG\_BYTES\_PER\_SECOND**](mf-mt-audio-avg-bytes-per-second-attribute.md)
-   [**MF\_MT\_AUDIO\_BLOCK\_ALIGNMENT**](mf-mt-audio-block-alignment-attribute.md)
-   [**MF\_MT\_AVG\_BITRATE**](mf-mt-avg-bitrate-attribute.md)

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
<td>Must be <strong>MFAudioFormat_AAC</strong>.</td>
</tr>
<tr class="odd">
<td><a href="mf-mt-audio-bits-per-sample-attribute"><strong>MF_MT_AUDIO_BITS_PER_SAMPLE</strong></a></td>
<td>Bits per sample.</td>
<td>Must be 16.</td>
</tr>
<tr class="even">
<td><a href="mf-mt-audio-samples-per-second-attribute"><strong>MF_MT_AUDIO_SAMPLES_PER_SECOND</strong></a></td>
<td>Samples per second.</td>
<td>Must match the input type.</td>
</tr>
<tr class="odd">
<td><a href="mf-mt-audio-num-channels-attribute"><strong>MF_MT_AUDIO_NUM_CHANNELS</strong></a></td>
<td>Number of channels.</td>
<td>Must match the input type.</td>
</tr>
<tr class="even">
<td><a href="mf-mt-audio-avg-bytes-per-second-attribute"><strong>MF_MT_AUDIO_AVG_BYTES_PER_SECOND</strong></a></td>
<td>Bit rate of the encoded AAC stream, in bytes per second.</td>
<td>The following values are supported:
<ul>
<li>12000</li>
<li>16000</li>
<li>20000</li>
<li>24000</li>
</ul>
The default value for both mono and stereo is 12000 (96 Kbps).<br/></td>
</tr>
<tr class="odd">
<td><a href="mf-mt-aac-payload-type">MF_MT_AAC_PAYLOAD_TYPE</a></td>
<td>The AAC payload type.</td>
<td>Optional. If set, the value must be zero, indicating that the stream contains raw_data_block elements only.<br/> Optional. If the attribute is not set, the default value is zero, indicating that the stream contains raw_data_block elements only (raw AAC). <br/> In Windows 7, if this attribute is set, the value must be zero.<br/> Starting in Windows 8, the value can be 0 (raw AAC) or 1 (ADTS AAC). <br/></td>
</tr>
<tr class="even">
<td><a href="mf-mt-aac-audio-profile-level-indication">MF_MT_AAC_AUDIO_PROFILE_LEVEL_INDICATION</a></td>
<td>The AAC audio profile and level.</td>
<td>Optional. The following values are supported:
<ul>
<li>0x29 (default)</li>
<li>0x2A</li>
<li>0x2B</li>
<li>0x2C</li>
<li>0x2E</li>
<li>0x2F</li>
<li>0x30</li>
<li>0x31</li>
<li>0x32</li>
<li>0x33</li>
</ul></td>
</tr>
</tbody>
</table>

The following table lists the values that can be used for the MF_MT_AAC_PROFILE_LEVEL_INDICATION attribute.

| MF_MT_AAC_PROFILE_LEVEL_INDICATION value | Profile                           |
|------------------------------------------|-----------------------------------|
| 0x29                                     | AAC Profile L2                    | 
| 0x2A                                     | AAC Profile L4                    | 
| 0x2B                                     | AAC Profile L5                    | 
| 0x2C                                     | High Efficiency v1 AAC Profile L2 | 
| 0x2E                                     | High Efficiency v1 AAC Profile L4 | 
| 0x2F                                     | High Efficiency v1 AAC Profile L5 | 
| 0x30                                     | High Efficiency v2 AAC Profile L2 | 
| 0x31                                     | High Efficiency v2 AAC Profile L3 | 
| 0x32                                     | High Efficiency v2 AAC Profile L4 | 
| 0x33                                     | High Efficiency v2 AAC Profile L5 | 

 

After the output type is set, the AAC encoder updates the type by adding the [**MF\_MT\_USER\_DATA**](mf-mt-user-data-attribute.md) attribute. This attribute contains the portion of the [**HEAACWAVEINFO**](https://docs.microsoft.com/windows/desktop/api/mmreg/ns-mmreg-heaacwaveinfo) structure that appears after the [**WAVEFORMATEX**](https://docs.microsoft.com/previous-versions/dd757713(v%3dvs.85)) structure (that is, after the **wfx** member). This is followed by the AudioSpecificConfig() data, as defined by ISO/IEC 14496-3.

Each output sample contains one compressed AAC frame with no header. This format is equivalent to the raw\_data\_block() element defined by MPEG-2. The [MF\_MT\_AAC\_PAYLOAD\_TYPE](mf-mt-aac-payload-type.md) attribute, if present in the output type, must be set to zero to indicate this payload type.

Each output sample contains one compressed AAC frame corresponding to 1024 PCM samples. For example, at 48 Khz sampling rate, the duration of one compressed frame is 21.33 msec.

If [MF\_MT\_AAC\_PAYLOAD\_TYPE](mf-mt-aac-payload-type.md) is zero (the default value), each output sample contains one raw\_data\_block() element as defined by ISO/IEC 13818-7.

## Example Media Types

Here is an example of the media types needed to encode from 44.1-kHz, 160-Kbps stereo audio to raw AAC

Input media type:



| Attribute                                                                                    | Value                  |
|----------------------------------------------------------------------------------------------|------------------------|
| [**MF\_MT\_MAJOR\_TYPE**](mf-mt-major-type-attribute.md)                                    | **MFMediaType\_Audio** |
| [**MF\_MT\_SUBTYPE**](mf-mt-subtype-attribute.md)                                           | **MFAudioFormat\_PCM** |
| [**MF\_MT\_AUDIO\_BITS\_PER\_SAMPLE**](mf-mt-audio-bits-per-sample-attribute.md)            | 16                     |
| [**MF\_MT\_AUDIO\_SAMPLES\_PER\_SECOND**](mf-mt-audio-samples-per-second-attribute.md)      | 44100                  |
| [**MF\_MT\_AUDIO\_NUM\_CHANNELS**](mf-mt-audio-num-channels-attribute.md)                   | 2                      |
| [**MF\_MT\_AUDIO\_AVG\_BYTES\_PER\_SECOND**](mf-mt-audio-avg-bytes-per-second-attribute.md) | 176400 (optional)      |
| [**MF\_MT\_AUDIO\_BLOCK\_ALIGNMENT**](mf-mt-audio-block-alignment-attribute.md)             | 4 (optional)           |
| [**MF\_MT\_ALL\_SAMPLES\_INDEPENDENT**](mf-mt-all-samples-independent-attribute.md)         | 1 (optional)           |
| [**MF\_MT\_AVG\_BITRATE**](mf-mt-avg-bitrate-attribute.md)                                  | 1411200 (optional)     |
| [**MF\_MT\_FIXED\_SIZE\_SAMPLES**](mf-mt-fixed-size-samples-attribute.md)                   | 1 (optional)           |



 

Output media type:



| Attribute                                                                                      | Value                                                                                           |
|------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| [**MF\_MT\_MAJOR\_TYPE**](mf-mt-major-type-attribute.md)                                      | **MFMediaType\_Audio**                                                                          |
| [**MF\_MT\_SUBTYPE**](mf-mt-subtype-attribute.md)                                             | **MFAudioFormat\_AAC**                                                                          |
| [**MF\_MT\_AUDIO\_BITS\_PER\_SAMPLE**](mf-mt-audio-bits-per-sample-attribute.md)              | 16                                                                                              |
| [**MF\_MT\_AUDIO\_SAMPLES\_PER\_SECOND**](mf-mt-audio-samples-per-second-attribute.md)        | 44100                                                                                           |
| [**MF\_MT\_AUDIO\_NUM\_CHANNELS**](mf-mt-audio-num-channels-attribute.md)                     | 2                                                                                               |
| [**MF\_MT\_AUDIO\_AVG\_BYTES\_PER\_SECOND**](mf-mt-audio-avg-bytes-per-second-attribute.md)   | 20000                                                                                           |
| [MF\_MT\_AAC\_PAYLOAD\_TYPE](mf-mt-aac-payload-type.md)                                       | 0 (optional)                                                                                    |
| [MF\_MT\_AAC\_AUDIO\_PROFILE\_LEVEL\_INDICATION](mf-mt-aac-audio-profile-level-indication.md) | 0x29 (optional)                                                                                 |
| [**MF\_MT\_AUDIO\_BLOCK\_ALIGNMENT**](mf-mt-audio-block-alignment-attribute.md)               | 1 (optional)                                                                                    |
| [**MF\_MT\_ALL\_SAMPLES\_INDEPENDENT**](mf-mt-all-samples-independent-attribute.md)           | 0 (optional)                                                                                    |
| [**MF\_MT\_AVG\_BITRATE**](mf-mt-avg-bitrate-attribute.md)                                    | 160000 (optional)                                                                               |
| [**MF\_MT\_USER\_DATA**](mf-mt-user-data-attribute.md)                                        | {0x00, 0x00, 0x29, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x12, 0x10} (optional) |



 

## Remarks

In the current implementation, every input sample must have a valid time and duration. To set the sample time, call [**IMFSample::SetSampleTime**](/windows/desktop/api/mfobjects/nf-mfobjects-imfsample-setsampletime). To set the sample duration, call [**IMFSample::SetSampleDuration**](/windows/desktop/api/mfobjects/nf-mfobjects-imfsample-setsampleduration).

If the sample time is not set, the encoder's [**IMFTransform::ProcessInput**](/windows/desktop/api/mftransform/nf-mftransform-imftransform-processinput) method returns **MF\_E\_NO\_SAMPLE\_TIMESTAMP**. If the sample duration is not set, the **ProcessInput** method returns **MF\_E\_NO\_SAMPLE\_DURATION**.

Sample duration can be calculated as follows:


```C++
LONGLONG hnsSampleDuration = 
    ( nAudioSamplesPerChannel * (LONGLONG)10000000 )/nSamplesPerSec;
```



where *nAudioSamplesPerChannel* is the number of PCM audio samples per channel in the input buffer, and *nSamplesPerSec* is the sampling rate, in samples per second.

> [!Note]  
> Due to a bug in the current implementation, if the sample duration is set to zero, the [**ProcessInput**](/windows/desktop/api/mftransform/nf-mftransform-imftransform-processinput) call succeeds, but a subsequent call to [**IMFTransform::ProcessOutput**](/windows/desktop/api/mftransform/nf-mftransform-imftransform-processoutput) will throw a divide-by-zero exception. To avoid this error, set a valid nonzero duration on each input sample.

 

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 7 \[desktop apps only\]<br/>                                              |
| Minimum supported server<br/> | Windows Server 2008 R2 \[desktop apps only\]<br/>                                 |
| DLL<br/>                      | <dl> <dt>Mfaacenc.dll</dt> </dl> |



## See also

<dl> <dt>

[Codec Objects](codecobjects.md)
</dt> <dt>

[**AAC Decoder**](aac-decoder.md)
</dt> <dt>

[AAC Media Types](aac-media-types.md)
</dt> <dt>

[Audio Media Types](audio-media-types.md)
</dt> <dt>

[MPEG-4 Support in Media Foundation](mpeg-4-support-in-media-foundation.md)
</dt> <dt>

[Supported Media Formats in Media Foundation](supported-media-formats-in-media-foundation.md)
</dt> </dl>

 

 




