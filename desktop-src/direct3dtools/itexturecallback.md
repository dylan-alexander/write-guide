---
Description: Callback to write a texture as a DDS file.
MS-HAID: vspixengine.ITextureCallback
MSHAttr:
- PreferredSiteName:MSDN
- PreferredLib:/library/windows/desktop
title: ITextureCallback interface
ms.topic: reference
ms.date: 05/31/2018
ms.assetid: 2558C90A-7235-4A36-859C-0E74BD0B712A
api_name: 
 - ITextureCallback
api_type: 
 - COM
api_location: 
 - vspixengine.h
topic_type: 
 - APIRef
 - kbSyntax

---

# <span id="vspixengine.itexturecallback"></span>ITextureCallback interface

Callback to write a texture as a DDS file.

## Members

The **ITextureCallback** interface inherits from the [**IUnknown**](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown) interface. **ITextureCallback** also has these types of members:

-   [Methods](#methods)

### <span id="methods"></span>Methods

The **ITextureCallback** interface has these methods.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th style="text-align: left;">Method</th><th style="text-align: left;">Description</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;"><a href="https://docs.microsoft.com/windows/desktop/direct3dtools/itexturecallback-resultcallback"><strong>ResultCallback</strong></a></td><td style="text-align: left;"><p>A callback that notifies the host that the .DDS (DirectDraw Surface) file containing results from the associated request are ready.</p></td></tr></tbody></table>

 

## Requirements

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><p>Header</p></td><td>Vspixengine.h</td></tr></tbody></table>

 

 



