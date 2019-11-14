---
Description: Many C++ applications clear the depth buffer before rendering each new frame.
ms.assetid: b8930211-82a1-4808-b042-1641e567cb6d
title: Clearing Depth Buffers (Direct3D 9)
ms.topic: article
ms.date: 05/31/2018
---

# Clearing Depth Buffers (Direct3D 9)

Many C++ applications clear the depth buffer before rendering each new frame. You can explicitly clear the depth buffer through Direct3D by calling [**IDirect3DDevice9::Clear**](https://msdn.microsoft.com/library/Bb174352(v=VS.85).aspx) and specifying D3DCLEAR\_ZBUFFER for the Flags parameter. The **IDirect3DDevice9::Clear** method allows you to specify an arbitrary depth value in the Z parameter.

## Related topics

<dl> <dt>

[Depth Buffers](depth-buffers.md)
</dt> </dl>

 

 



