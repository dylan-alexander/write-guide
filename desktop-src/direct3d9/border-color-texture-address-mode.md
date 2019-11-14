---
Description: The border color texture address mode, identified by the D3DTADDRESS\_BORDER member of the D3DTEXTUREADDRESS enumerated type, causes Direct3D to use an arbitrary color, known as the border color, for any texture coordinates outside the range of 0.0 through 1.0, inclusive.
ms.assetid: 689dbda1-0692-411d-9727-2fdf1df960ec
title: Border Color Texture Address Mode (Direct3D 9)
ms.topic: article
ms.date: 05/31/2018
---

# Border Color Texture Address Mode (Direct3D 9)

The border color texture address mode, identified by the D3DTADDRESS\_BORDER member of the [**D3DTEXTUREADDRESS**](https://msdn.microsoft.com/en-us/library/Bb172614(v=VS.85).aspx) enumerated type, causes Direct3D to use an arbitrary color, known as the border color, for any texture coordinates outside the range of 0.0 through 1.0, inclusive.

In the following illustration, the application specifies that the texture be applied to the primitive using a red border.

![illustration of a texture and a texture with a red border](images/border.png)

Applications set the border color by calling [**IDirect3DDevice9::SetSamplerState**](https://msdn.microsoft.com/library/Bb174456(v=VS.85).aspx). Set the first parameter for the call to the desired texture stage identifier, the second parameter to the D3DSAMP\_BORDERCOLOR stage state value, and the third parameter to the new RGBA border color.

## Related topics

<dl> <dt>

[Texture Addressing Modes](texture-addressing-modes.md)
</dt> </dl>

 

 



