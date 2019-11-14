---
title: IDXCoreAdapterList::GetAdapter
description: Retrieves a specific adapter by index from a DXCore adapter list object.
ms.localizationpriority: low
ms.topic: article
ms.date: 06/20/2019
---

# IDXCoreAdapterList::GetAdapter method

> [!NOTE]
> **Some information relates to pre-released product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.**

> [!IMPORTANT]
> The feature described in this topic is available in pre-release versions of the [Windows 10 Insider Preview](https://www.microsoft.com/software-download/windowsinsiderpreviewSDK).

Retrieves a specific adapter by index from a DXCore adapter list object. For programming guidance, and code examples, see [Using DXCore to enumerate adapters](/windows/win32/dxcore/dxcore-enum-adapters).

## Syntax

```cpp
virtual HRESULT STDMETHODCALLTYPE GetAdapter(
  uint32_t index,
  REFIID riid,
  _COM_Outptr_ void **ppvAdapter) = 0;

template<class T>
HRESULT STDMETHODCALLTYPE GetAdapter( 
  uint32_t index,
  _COM_Outptr_ T **ppvAdapter);
```

## Parameters

### index

Type: **uint32_t**

A zero-based index, identifying an adapter instance within the DXCore adapter list.

### riid

Type: **REFIID**

A reference to the globally unique identifier (GUID) of the interface that you wish to be returned in *ppvAdapter*. This is expected to be the interface identifier (IID) of [IDXCoreAdapter](/windows/win32/dxcore/dxcore_interface/nn-dxcore_interface-idxcoreadapter).

### ppvAdapter [out]

Type: **void\*\***

The address of a pointer to an interface with the IID specified in the *riid* parameter. Upon successful return, *\*ppvAdapter* (the dereferenced address) contains a pointer to the DXCore adapter created.

## Returns

Type: **[HRESULT](/windows/win32/com/structure-of-com-error-codes)**

If the function succeeds, it returns **S_OK**. Otherwise, it returns an [**HRESULT**](/windows/win32/com/structure-of-com-error-codes) [error code](/windows/win32/com/com-error-codes-10).

|Return value|Description|
|-|-|
|DXGI_ERROR_DEVICE_REMOVED|The *index* is valid, but the adapter is no longer in a valid state.|
|E_INVALIDARG|The provided *index* is not valid.|
|E_NOINTERFACE|An invalid value was provided for *riid*.|
|E_POINTER|`nullptr` was provided for *ppvAdapter*.|

## Remarks

Multiple calls passing an index that represents the same adapter return identical interface pointers, even across different adapter lists. As a result, it's safe to compare interface pointers to determine whether multiple pointers refer to the same adapter object.

## See also

[IDXCoreAdapterList](/windows/win32/dxcore/dxcore_interface/nn-dxcore_interface-idxcoreadapterlist), [DXCore Reference](/windows/win32/dxcore/dxcore-reference), [Using DXCore to enumerate adapters](/windows/win32/dxcore/dxcore-enum-adapters)
