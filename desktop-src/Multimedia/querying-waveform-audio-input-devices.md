---
title: Querying Waveform-Audio Input Devices
description: Querying Waveform-Audio Input Devices
ms.assetid: 573b33bc-f445-496e-a0e6-0194d30bb668
keywords:
- waveform audio,querying input devices
- waveform-audio interface,querying input devices
- recording waveform audio,querying input devices
- querying waveform-audio input devices
ms.topic: article
ms.date: 05/31/2018
---

# Querying Waveform-Audio Input Devices

Before recording waveform audio, you should call the [**waveInGetDevCaps**](https://msdn.microsoft.com/en-us/library/Dd743841(v=VS.85).aspx) function to determine the waveform-audio input capabilities of the system. This function fills a [**WAVEINCAPS**](https://msdn.microsoft.com/en-us/library/Dd743839(v=VS.85).aspx) structure with information about the capabilities of a specified device. This information includes the manufacturer and product identifiers, a product name for the device, and the version number of the device driver. In addition, the **WAVEINCAPS** structure provides information about the standard waveform-audio formats that the device supports.

## Related topics

<dl> <dt>

[Recording Waveform Audio](recording-waveform-audio.md)
</dt> </dl>

 

 




