---
title: Volume tiled resources
description: Volume (3D) textures can be used as tiled resources, noting that tile resolution is three-dimensional.
ms.assetid: F670D15D-BC0F-4F90-99C1-A35192FE8980
ms.localizationpriority: high
ms.topic: article
ms.date: 05/31/2018
---

# Volume tiled resources

Volume (3D) textures can be used as tiled resources, noting that tile resolution is three-dimensional.

-   [Overview](#overview)
-   [Tiled Resource APIs](#tiled-resource-apis)
-   [Related topics](#related-topics)

## Overview

Tiled resources decouple a D3D Resource object from its backing memory (resources in the past had a 1:1 relationship with their backing memory). This allows for a variety of interesting scenarios such as streaming in texture data and reusing or reducing memory usage.

2D texture tiled resources are supported in D3D11.2. Optional support for 3D tiled textures is available for D3D12 and D3D11.3 (refer to [**D3D12\_TILED\_RESOURCES\_TIER**](/windows/desktop/api/d3d12/ne-d3d12-d3d12_tiled_resources_tier)).

The typical resource dimensions used in tiling are 4 x 4 tiles for 2D textures, and 4 x 4 x 4 tiles for 3D textures.



| Bits/pixel (1 sample/pixel) | Tile dimensions (pixels, w x h x d) |
|-----------------------------|-------------------------------------|
| 8                           | 64x32x32                            |
| 16                          | 32x32x32                            |
| 32                          | 32x32x16                            |
| 64                          | 32x16x16                            |
| 128                         | 16x16x16                            |
| BC 1,4                      | 128x64x16                           |
| BC 2,3,5,6,7                | 64x64x16                            |

Note the following formats are not supported with tiled resources: 96bpp formats, video formats, R1\_UNORM, R8G8\_B8G8\_UNORM, R8R8\_G8B8\_UNORM.

In the diagrams below dark gray represents NULL tiles.

-   [Texture 3D Tiled Resource default mapping (most detailed mip)](#texture-3d-tiled-resource-default-mapping-most-detailed-mip)
-   [Texture 3D Tiled Resource default mapping (second most detailed mip)](#texture-3d-tiled-resource-default-mapping-second-most-detailed-mip)
-   [Texture 3D Tiled Resource (most detailed mip)](#texture-3d-tiled-resource-most-detailed-mip)
-   [Texture 3D Tiled Resource (second most detailed mip)](#texture-3d-tiled-resource-second-most-detailed-mip)
-   [Texture 3D Tiled Resource (Single Tile)](#texture-3d-tiled-resource-single-tile)
-   [Texture 3D Tiled Resource (Uniform Box)](#texture-3d-tiled-resource-uniform-box)

### Texture 3D Tiled Resource default mapping (most detailed mip)

![default mapping of a tiled 3 dimensional resource](images/vtr-tex3d-default-1.png)

### Texture 3D Tiled Resource default mapping (second most detailed mip)

![shows the second most detailed mip](images/vtr-tex3d-default-2.png)

### Texture 3D Tiled Resource (most detailed mip)

The following code sets up a 3D tiled resource at the most detailed mip.

``` syntax
D3D12_TILED_RESOURCE_COORDINATE trCoord;
trCoord.X = 1;
trCoord.Y = 0;
trCoord.Z = 0;
trCoord.Subresource = 0;

D3D12_TILE_REGION_SIZE trSize;
trSize.bUseBox = false;
trSize.NumTiles = 63;
```

![most detailed mip for a three dimensional texture](images/vtr-tex3d-default-1b.png)

### Texture 3D Tiled Resource (second most detailed mip)

The following code sets up a 3D tiled resource, and the second most detailed mip:

``` syntax
D3D12_TILED_RESOURCE_COORDINATE trCoord;
trCoord.X = 1;
trCoord.Y = 0;
trCoord.Z = 0;
trCoord.Subresource = 1;

D3D12_TILE_REGION_SIZE trSize;
trSize.bUseBox = false;
trSize.NumTiles = 6;
```

![second most detailed mip for a three dimensional texture](images/vtr-tex3d-default-2b.png)

### Texture 3D Tiled Resource (Single Tile)

The following code sets up a Single Tile resource:

``` syntax
D3D12_TILED_RESOURCE_COORDINATE trCoord;
trCoord.X = 1;
trCoord.Y = 1;
trCoord.Z = 1;
trCoord.Subresource = 0;

D3D12_TILE_REGION_SIZE trSize;
trSize.bUseBox = true;
trSize.NumTiles = 27;
trSize.Width = 3;
trSize.Height = 3;
trSize.Depth = 3;
```

![a single tiled three dimensional resource](images/vtr-tex3d-single.png)

### Texture 3D Tiled Resource (Uniform Box)

The following code sets up a Uniform Box tiled resource (note the statement `trSize.bUseBox = true;) :`

``` syntax
D3D12_TILED_RESOURCE_COORDINATE trCoord;
trCoord.X = 0;
trCoord.Y = 1;
trCoord.Z = 0;
trCoord.Subresource = 0;

D3D12_TILE_REGION_SIZE trSize;
trSize.bUseBox = true;
trSize.NumTiles = 27;
trSize.Width = 3;
trSize.Height = 3;
trSize.Depth = 3;
```

![a uniform box](images/vtr-tex3d-uniform.png)

## Tiled Resource APIs

The same API calls are used for both 2D and 3D tiled resources:

Enums

-   [**D3D12\_TILED\_RESOURCES\_TIER**](/windows/desktop/api/d3d12/ne-d3d12-d3d12_tiled_resources_tier) : determines the level of tiled resource support.
-   [**D3D12\_FORMAT\_SUPPORT2**](/windows/desktop/api/d3d12/ne-d3d12-d3d12_format_support2) : used to test for tiled resource support.
-   [**D3D12\_MULTISAMPLE\_QUALITY\_LEVEL\_FLAGS**](/windows/desktop/api/d3d12/ne-d3d12-d3d12_multisample_quality_level_flags) : determines tiled resource support in a multi-sampling resource.
-   [**D3D12\_TILE\_COPY\_FLAGS**](/windows/desktop/api/d3d12/ne-d3d12-d3d12_tile_copy_flags) : holds flags for copying to and from swizzled tiled resources and linear buffers.

Structs

-   [**D3D12\_TILED\_RESOURCE\_COORDINATE**](/windows/desktop/api/d3d12/ns-d3d12-d3d12_tiled_resource_coordinate) : holds the x, y, and z co-ordinate, and subresource reference. Note there is a helper structure: [**CD3DX12\_TILED\_RESOURCE\_COORDINATE**](cd3dx12-tiled-resource-coordinate.md).
-   [**D3D12\_TILE\_REGION\_SIZE**](/windows/desktop/api/d3d12/ns-d3d12-d3d12_tile_region_size) : specifies the size, and number of tiles, of the tiled region.
-   [**D3D12\_TILE\_SHAPE**](/windows/desktop/api/d3d12/ns-d3d12-d3d12_tile_shape) : the tile shape as a width, height and depth in texels.
-   [**D3D12\_FEATURE\_DATA\_D3D12\_OPTIONS**](/windows/desktop/api/d3d12/ns-d3d12-d3d12_feature_data_d3d12_options) : holds the supported tile resource tier level and a boolean, *VolumeTiledResourcesSupported*, indicated whether volume tiled resources are supported.

Methods

-   [**ID3D12Device::CheckFeatureSupport**](/windows/desktop/api/d3d12/nf-d3d12-id3d12device-checkfeaturesupport) : used to determine what features, and at what tier, are supported by the current hardware.
-   [**ID3D12GraphcisCommandList::CopyTiles**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-copytiles) : copies tiles from buffer to tiled resource or vice versa.
-   [**ID3D12CommandQueue::UpdateTileMappings**](/windows/desktop/api/d3d12/nf-d3d12-id3d12commandqueue-updatetilemappings) : updates mappings of tile locations in tiled resources to memory locations in a resource heap.
-   [**ID3D12CommandQueue::CopyTileMappings**](/windows/desktop/api/d3d12/nf-d3d12-id3d12commandqueue-copytilemappings) : copies mappings from a source tiled resource to a destination tiled resource.
-   [**ID3D12CommandQueue::GetResourceTiling**](/windows/desktop/api/d3d12/nf-d3d12-id3d12device-getresourcetiling) : gets info about how a tiled resource is broken into tiles.

## Related topics
* [Resource Binding](resource-binding.md)
