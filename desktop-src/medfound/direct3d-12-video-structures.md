---
Description: This section contains reference information for the Microsoft Direct3D 12 video API structures.
ms.assetid: 
title: Direct3D 12 Video Structures
ms.topic: article
ms.date: 06/03/2019
---

# Direct3D 12 Video Structures

This section contains reference information for the Microsoft Direct3D 12 video API structures.

## In this section

| Topic                                                                                | Description                                                                                              |
|---------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| [D3D12_FEATURE_DATA_VIDEO_DECODE_CONVERSION_SUPPORT](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_feature_data_video_decode_conversion_support)  | Retrieves the list of supported profiles.|
| [D3D12_FEATURE_DATA_VIDEO_DECODE_FORMATS](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_feature_data_video_decode_formats)  | Retrieves the list of supported formats.|
| [D3D12_FEATURE_DATA_VIDEO_DECODE_HISTOGRAM](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_feature_data_video_decode_histogram)  | Provides data for calls to ID3D12VideoDevice::CheckFeatureSupport when the feature specified is D3D12_FEATURE_VIDEO_DECODE_HISTOGRAM.|
| [D3D12_FEATURE_DATA_VIDEO_DECODE_PROFILES](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_feature_data_video_decode_profiles)  | Retrieves the list of supported profiles.|
| [D3D12_FEATURE_DATA_VIDEO_DECODE_SUPPORT](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_feature_data_video_decode_support)  | Retrieves support information for video decoding.|
| [D3D12_FEATURE_DATA_VIDEO_PROCESS_MAX_INPUT_STREAMS](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_feature_data_video_process_max_input_streams)  | Retrieves the maximum number of enabled input streams supported by the video processor.|
| [D3D12_FEATURE_DATA_VIDEO_PROCESS_REFERENCE_INFO](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_feature_data_video_process_reference_info)  | Retrieves the number of past and future reference frames required for the specified deinterlace mode, filter, rate conversion, or auto processing features.|
| [D3D12_FEATURE_DATA_VIDEO_PROCESS_SUPPORT](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_feature_data_video_process_support)  | Provides data for calls to ID3D12VideoDevice::CheckFeatureSupport when the feature specified is D3D12_FEATURE_VIDEO_PROCESS_SUPPORT.|
| [D3D12_QUERY_DATA_VIDEO_DECODE_STATISTICS](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_query_data_video_decode_statistics)  | Represents data for a video decode statistics query invoked by calling ID3D12VideoDecodeCommandList::EndQuery.|
| [D3D12_VIDEO_DECODER_DESC](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decoder_desc)  | Describes a ID3D12VideoDecoder.|
| [D3D12_VIDEO_DECODER_HEAP_DESC](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decoder_heap_desc)  | Describes a ID3D12VideoDecoderHeap.|
| [D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decode_compressed_bitstream)  | Represents a compressed bitstream from which video is decoded.|
| [D3D12_VIDEO_DECODE_CONFIGURATION](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decode_configuration)  | Describes the configuration for a video decoder.|
| [D3D12_VIDEO_DECODE_CONVERSION_ARGUMENTS](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decode_conversion_arguments)  | Specifies the parameters for decode output conversion.|
| [D3D12_VIDEO_DECODE_CONVERSION_ARGUMENTS1](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decode_conversion_arguments1)  | Specifies the parameters for decode output conversion.|
| [D3D12_VIDEO_DECODE_FRAME_ARGUMENT](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decode_frame_argument)  | Represents the decode parameters for a frame.|
| [D3D12_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decode_input_stream_arguments)  | Specifies the parameters for the input stream for a video decode operation.|
| [D3D12_VIDEO_DECODE_OUTPUT_HISTOGRAM](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decode_output_histogram)  | Represents the histogram output buffer for a single component.|
| [D3D12_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decode_output_stream_arguments)  | Specifies the parameters for the output stream for a video decode operation.|
| [D3D12_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS1](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decode_output_stream_arguments1)  | Specifies the parameters for the output stream for a video decode operation.|
| [D3D12_VIDEO_DECODE_REFERENCE_FRAMES](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decode_reference_frames)  | Contains the list of reference frames for the current decode operation.|
| [D3D12_VIDEO_DECODE_SUB_SAMPLE_MAPPING_BLOCK](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_decode_sub_sample_mapping_block)  | Defines the encryption byte mapping of sub samples for video decoding.|
| [D3D12_VIDEO_FORMAT](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_format)  | Defines the combination of a pixel format and color space for a resource content description.|
| [D3D12_VIDEO_PROCESS_ALPHA_BLENDING](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_process_alpha_blending)  | Specifies alpha blending parameters for video processing.|
| [D3D12_VIDEO_PROCESS_FILTER_RANGE](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_process_filter_range)  | Defines the range of supported values for an image filter.|
| [D3D12_VIDEO_PROCESS_INPUT_STREAM](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_process_input_stream)  | Contains input information for the video processor blend functionality.|
| [D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_process_input_stream_arguments)  | Specifies input stream arguments for an input stream passed to ID3D12VideoCommandList::ProcessFrames.|
| [D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_process_input_stream_desc)  | Specifies the parameters for the input stream for a video process operation.|
| [D3D12_VIDEO_PROCESS_INPUT_STREAM_RATE](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_process_input_stream_rate)  | Provides information about the stream rate.|
| [D3D12_VIDEO_PROCESS_LUMA_KEY](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_process_luma_key)  | Specifies the settings used for luma keying.|
| [D3D12_VIDEO_PROCESS_OUTPUT_STREAM](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_process_output_stream)  | Represents the output stream for video processing commands.|
| [D3D12_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_process_output_stream_arguments)  | Specifies output stream arguments for the output passed to ID3D12VideoCommandList::ProcessFrames.|
| [D3D12_VIDEO_PROCESS_OUTPUT_STREAM_DESC](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_process_output_stream_desc)  | Specifies output stream arguments for the output passed to ID3D12VideoProcessCommandList::ProcessFrames.|
| [D3D12_VIDEO_PROCESS_REFERENCE_SET](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_process_reference_set)  | Contains the reference frames needed to perform video processing.|
| [D3D12_VIDEO_PROCESS_TRANSFORM](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_process_transform)  | Specifies transform parameters for video processing.|
| [D3D12_VIDEO_SAMPLE](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_sample)  | Describes the width, height, format, and color space of a picture buffer.|
| [D3D12_VIDEO_SCALE_SUPPORT](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_scale_support)  | Describes the supported scaling range of output sizes for a video scaler.|
| [D3D12_VIDEO_SIZE_RANGE](/windows/desktop/api/d3d12video/ns-d3d12video-d3d12_video_size_range)  | Describes the range of supported sizes for a video scaler.|



## Related topics

<dl> <dt>

[Direct3D 12 Video APIs](direct3d-12-video-apis.md)
</dt> </dl>

 

 



