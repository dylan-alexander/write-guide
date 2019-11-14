---
Description: Request for offline analysis data.
MS-HAID: vspixengine.IOfflineAnalysisRequest
MSHAttr:
- PreferredSiteName:MSDN
- PreferredLib:/library/windows/desktop
title: IOfflineAnalysisRequest interface
ms.topic: reference
ms.date: 05/31/2018
ms.assetid: 1E438545-D4C4-45A7-918E-D3D9DC06BA08
api_name: 
 - IOfflineAnalysisRequest
api_type: 
 - COM
api_location: 
 - vspixengine.h
topic_type: 
 - APIRef
 - kbSyntax

---

# <span id="vspixengine.iofflineanalysisrequest"></span>IOfflineAnalysisRequest interface

Request for offline analysis data.

## Members

The **IOfflineAnalysisRequest** interface inherits from the [**IUnknown**](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown) interface. **IOfflineAnalysisRequest** also has these types of members:

-   [Methods](#methods)

### <span id="methods"></span>Methods

The **IOfflineAnalysisRequest** interface has these methods.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th style="text-align: left;">Method</th><th style="text-align: left;">Description</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;"><a href="https://docs.microsoft.com/windows/desktop/direct3dtools/iofflineanalysisrequest-cancelofflineanalysisasync-dword"><strong>CancelOfflineAnalysisAsync</strong></a></td><td style="text-align: left;"><p>Requests to cancel offline analysis in an offline analysis request.</p></td></tr><tr class="even"><td style="text-align: left;"><a href="https://docs.microsoft.com/windows/desktop/direct3dtools/iofflineanalysisrequest-requestofflineanalysisasync-enumofflineanalysissource-bstr-bstr-dword-bstr-dword-bstr-iofflineanalysiscallback-ptr"><strong>RequestOfflineAnalysisAsync</strong></a></td><td style="text-align: left;"><p>Requests to run offline analysis with the specified source, manifest, parameters and of the specified frame.</p></td></tr></tbody></table>

 

## Requirements

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><p>Header</p></td><td>Vspixengine.h</td></tr></tbody></table>

 

 



