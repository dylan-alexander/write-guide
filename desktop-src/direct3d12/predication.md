---
title: Predication
description: Predication is a feature that enables the GPU rather than the CPU to determine to not draw, copy or dispatch an object.
ms.assetid: '5c5138c7-f6e8-4646-961a-0e2312b5356b'
ms.localizationpriority: high
ms.topic: article
ms.date: 05/31/2018
---

# Predication

Predication is a feature that enables the GPU rather than the CPU to determine to not draw, copy or dispatch an object.

-   [Overview](#overview)
-   [SetPredication](#setpredication)
-   [Related topics](#related-topics)

## Overview

The typical use of predication is with occlusion; if a bounding box is drawn and is occluded, there is obviously no point in drawing the object itself. In this situation the drawing of the object can be "predicated" , enabling its removal from actual rendering by the GPU.

Unlike Direct3D 11, predication is decoupled from queries, and is expanded in Direct3D 12 to enable an application to predicate objects based on any reasoning the app developer may decide on (not just occlusion).

## SetPredication

Predication can be set based on the value of 64-bits within a buffer (refer to [**D3D12\_PREDICATION\_OP**](/windows/desktop/api/d3d12/ne-d3d12-d3d12_predication_op)).

When the GPU executes a [**SetPredication**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-setpredication) command it snaps the value in the buffer. Future changes to the data in the buffer do not retroactively affect the predication state.

If the input parameter Buffer is NULL, then predication is disabled.

Predication hints are not present in the D3D12 API, and predication is allowed on direct and compute command lists. The source buffer can be in any heap type (default, upload, readback).

The core runtime will validate the following:

-   *AlignedBufferOffset* is a multiple of 8 bytes
-   The resource is a buffer
-   The operation is a valid member of the enumeration
-   [**SetPredication**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-setpredication) cannot be called from within a bundle
-   The command list type supports predication
-   The offset does not exceed the buffer size

The debug layer will issue an error if the source buffer is not in the D3D12\_RESOURCE\_STATE\_VERTEX\_AND\_CONSTANT\_BUFFER state.

The set of operations which can be predicated are:

-   [**DrawInstanced**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-drawinstanced)
-   [**DrawIndexedInstanced**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-drawindexedinstanced)
-   [**Dispatch**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-dispatch)
-   [**CopyTextureRegion**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-copytextureregion)
-   [**CopyBufferRegion**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-copybufferregion)
-   [**CopyResource**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-copyresource)
-   [**CopyTiles**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-copytiles)
-   [**ResolveSubresource**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-resolvesubresource)
-   [**ClearDepthStencilView**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-cleardepthstencilview)
-   [**ClearRenderTargetView**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-clearrendertargetview)
-   [**ClearUnorderedAccessViewUint**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-clearunorderedaccessviewuint)
-   [**ClearUnorderedAccessViewFloat**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-clearunorderedaccessviewfloat)
-   [**ExecuteIndirect**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-executeindirect)

[**ExecuteBundle**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-executebundle) is not predicated itself. Instead, individual operations from the list above which are contained in side of the bundle are predicated.

The ID3D12GraphicsCommandList methods [**ResolveQueryData**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-resolvequerydata), [**BeginQuery**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-beginquery) and [**EndQuery**](/windows/desktop/api/d3d12/nf-d3d12-id3d12graphicscommandlist-endquery) are not predicated.

## Related topics

<dl> <dt>

[Counters and Queries](counters-and-queries.md)
</dt> <dt>

[Performance Measurement](performance-measurement.md)
</dt> <dt>

[Predication queries walk-through](predication-queries.md)
</dt> </dl>

 

 




