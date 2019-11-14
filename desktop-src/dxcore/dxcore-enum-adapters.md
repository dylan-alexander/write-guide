---
title: Using DXCore to enumerate adapters
description: A look at the main features of DXCore with some code examples, as well as a full source code listing of a minimal DXCore application.
ms.localizationpriority: high
ms.topic: article
ms.date: 06/20/2019
---

# Using DXCore to enumerate adapters

> [!NOTE]
> **Some information relates to pre-released product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.**

> [!IMPORTANT]
> The feature described in this topic is available in pre-release versions of the [Windows 10 Insider Preview](https://www.microsoft.com/software-download/windowsinsiderpreviewSDK).

DXCore is an adapter enumeration API for DirectX devices, so some of its facilities overlap with those of [DXGI](/windows/win32/direct3ddxgi/dx-graphics-dxgi).

DXCore enables the exposure of new device types to user mode, such as MCDM (Microsoft Compute Driver Model), for use with [Direct3D 12](/windows/win32/direct3d12/directx-12-programming-guide), [DirectML](/windows/win32/direct3d12/dml), and [Windows Machine Learning](/windows/ai/windows-ml/). DXCore, unlike DXGI, views the adapters as *processors*, and it ignores any information about display-related technology.

In the next few sections, we'll take a look at the main features of DXCore with some code examples (written in [C++/WinRT](/windows/uwp/cpp-and-winrt-apis)). The code examples shown below are extracted from the full source code listing that you can find in the topic [Minimal DXCore application](dxcore-source-code.md).

## Create an adapter factory

You begin DXCore adapter enumeration by creating an adapter factory object, which is represented by the [**IDXCoreAdapterFactory**](/windows/win32/dxcore/dxcore_interface/nn-dxcore_interface-idxcoreadapterfactory) interface. To create a factory, include the `dxcore.h` header file, and call the [**DXCoreCreateAdapterFactory**](/windows/win32/dxcore/dxcore/nf-dxcore-dxcorecreateadapterfactory) free function.

```cppwinrt
#include <dxcore.h>
...
winrt::com_ptr<IDXCoreAdapterFactory> adapterFactory;
winrt::check_hresult(::DXCoreCreateAdapterFactory(adapterFactory.put()));
```

## Retrieve an adapter list

Unlike with DXGI, a newly-created DXCore adapter factory doesn't automatically create a snapshot of the adapter state of the system. Instead, DXCore creates that snapshot when you explicitly retrieve an adapter list object, which is represented by the [**IDXCoreAdapterList**](/windows/win32/dxcore/dxcore_interface/nn-dxcore_interface-idxcoreadapterlist) interface.

```cppwinrt
winrt::com_ptr<IDXCoreAdapterList> d3D12CoreComputeAdapters;
GUID attributes[]{ DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE };
winrt::check_hresult(
    adapterFactory->CreateAdapterList(_countof(attributes),
        attributes,
        d3D12CoreComputeAdapters.put()));
```

## Select an appropriate adapter from the list

This section demonstrates how, given an adapter list object, you could find the first hardware adapter in the list.

The [**IDXCoreAdapterList::GetAdapterCount**](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapterlist-getadaptercount) method tells you the number of elements in the list, and [**IDXCoreAdapterList::GetAdapter**](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapterlist-getadapter) retrieves a specific adapter by index.

You can then query the properties of that adapter, by following these steps.

- First, to confirm that it's valid to retrieve the value of a given property for this adapter on this operating system version, you call [**IDXCoreAdapter::IsPropertySupported**](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapter-ispropertysupported). Pass a value of the [**DXCoreAdapterProperty**](/windows/win32/dxcore/dxcore_interface/ne-dxcore_interface-dxcoreadapterproperty) enumeration to identify which property you're querying about.
- Optionally confirm the size of the property value with a call to [**IDXCoreAdapter::GetPropertySize**](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapter-getpropertysize). For a property such as **DXCoreAdapterProperty::IsHardware**, which is a simple Boolean, this step isn't necessary.
- And, finally, retrieve the property's value by calling [**IDXCoreAdapter::GetProperty**](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapter-getproperty).

```cppwinrt
winrt::com_ptr<IDXCoreAdapter> preferredAdapter;

const uint32_t count{ d3D12CoreComputeAdapters->GetAdapterCount() };

for (uint32_t i = 0; i < count; ++i)
{
    winrt::com_ptr<IDXCoreAdapter> candidateAdapter;
    winrt::check_hresult(
        d3D12CoreComputeAdapters->GetAdapter(i, candidateAdapter.put()));

    bool isHardware{ false };
    winrt::check_hresult(candidateAdapter->GetProperty(
        DXCoreAdapterProperty::IsHardware,
        &isHardware));

    if (isHardware)
    {
        // Choose the first hardware adapter, and stop looping.
        preferredAdapter = candidateAdapter;
        break;
    }

    // Otherwise, ensure that (as long as there are *any* adapters) we'll
    // at least choose one.
    if (!preferredAdapter)
    {
        preferredAdapter = candidateAdapter;
    }
}
```

## Select the preferred adapter by sorting an adapter list

You can sort a DXCore adapter list by calling the [IDXCoreAdapterList::Sort](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapterlist-sort) method.

The [DXCoreAdapterPreference](/windows/win32/dxcore/dxcore_interface/ne-dxcore_interface-dxcoreadapterpreference) enumeration defines values that representing sort criteria. Pass an array of those values to **Sort**, and then read off the first adapter in the resulting sorted list.

To determine whether a sort type is going to be understood by **Sort**, first call [IDXCoreAdapterList::IsAdapterPreferenceSupported](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapterlist-isadapterpreferencesupported).

```cppwinrt
winrt::com_ptr<IDXCoreAdapter> TryFindHardwareHighPerformanceGraphicsAdapter()
{
    // You begin DXCore adapter enumeration by creating an adapter factory.
    winrt::com_ptr<IDXCoreAdapterFactory> adapterFactory;
    winrt::check_hresult(::DXCoreCreateAdapterFactory(adapterFactory.put()));

    // From the factory, retrieve a list of all the Direct3D 12 Graphics adapters.
    winrt::com_ptr<IDXCoreAdapterList> d3D12GraphicsAdapters;
    GUID attributes[]{ DXCORE_ADAPTER_ATTRIBUTE_D3D12_GRAPHICS };
    winrt::check_hresult(
        adapterFactory->CreateAdapterList(_countof(attributes),
            attributes,
            d3D12GraphicsAdapters.put()));

    DXCoreAdapterPreference sortPreferences[]{
        DXCoreAdapterPreference::Hardware, DXCoreAdapterPreference::HighPerformance };

    // Ask the OS to sort for the highest performance hardware adapter.
    winrt::check_hresult(d3D12GraphicsAdapters->Sort(_countof(sortPreferences), sortPreferences));

    winrt::com_ptr<IDXCoreAdapter> preferredAdapter;

    if (d3D12GraphicsAdapters->GetAdapterCount() > 0)
    {
        winrt::check_hresult(d3D12GraphicsAdapters->GetAdapter(0, preferredAdapter.put()));
    }

    return preferredAdapter;
}
```

## Query and set adapter state (properties)

You can retrieve and set the state of a specified state item of an adapter by calling the [**IDXCoreAdapter::QueryState**](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapter-querystate) and [**IDXCoreAdapter::SetState**](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapter-setstate) methods.

```cppwinrt
void SetDesiredMemoryReservation(winrt::com_ptr<IDXCoreAdapter> const& adapter, uint64_t reservation)
{
    DXCoreAdapterMemoryBudgetNodeSegmentGroup nodeSegmentGroup{};
    nodeSegmentGroup.nodeIndex = 0;
    nodeSegmentGroup.segmentGroup = DXCoreSegmentGroup::Local;

    DXCoreAdapterMemoryBudget memoryBudget{};
    winrt::check_hresult(adapter->QueryState(
        DXCoreAdapterState::AdapterMemoryBudget,
        &nodeSegmentGroup,
        &memoryBudget));

    // Clamp the reservation to what's available.
    reservation = std::min<uint64_t>(reservation, memoryBudget.availableForReservation);

    winrt::check_hresult(adapter->SetState(
        DXCoreAdapterState::AdapterMemoryBudget,
        &nodeSegmentGroup,
        &reservation));
}
```

In practice, before calling **QueryState** and **SetState**, you should call [IsQueryStateSupported](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapter-isquerystatesupported) to confirm that querying the state kind is available for this adapter and operating system (OS).

## Adapter list freshness

Should an adapter list become stale due to changing system conditions, it will be marked as such. You can determine an adapter list's freshness by polling its [**IDXCoreAdapterList::IsStale**](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapterlist-isstale) method.

More conveniently, though, you can subscribe to notifications for conditions such as staleness. To do that, pass [**DXCoreNotificationType::AdapterListStale**](/windows/win32/dxcore/dxcore_interface/ne-dxcore_interface-dxcorenotificationtype) to [**IDXCoreAdapterFactory::RegisterEventNotification**](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapterfactory-registereventnotification), and safely store the returned cookie for use later.

```cppwinrt
uint32_t m_eventCookie = 0;
...
winrt::check_hresult(factory->RegisterEventNotification(
    m_adapters.get(),
    DXCoreNotificationType::AdapterListStale,
    OnAdapterListStale,
    this,
    &m_eventCookie));
...
static void WINAPI OnAdapterListStale(
    DXCoreNotificationType notificationType,
    IUnknown* staleObject,
    void* context)
{
    ...
}
```

You can then generate a new, current, adapter list object from the factory object that you already have. Handling these conditions is critical to your ability to seamlessly respond to events such as adapter arrival and removal (whether that be a GPU, or a specialized compute adapter), and to appropriately shift workloads in response.

Before you destroy the adapter list object, you must use the cookie value to unregister that object from notifications by calling [IDXCoreAdapterFactory::UnregisterEventNotification](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapterfactory-unregistereventnotification). If you don't unregister, then a fatal exception is raised when the situation is detected.

```cppwinrt
HRESULT hr = factory->UnregisterEventNotification(m_eventCookie);
```

## Display information

> [!NOTE]
> DXCore doesn't itself provide any display information. Where necessary, you should use the Windows Runtime [**DisplayMonitor**](/uwp/api/windows.devices.display.displaymonitor) class to retrieve this information. An adapter's [**LUID**](/windows/win32/api/winnt/ns-winnt-luid) provides a common identifier that you can use to map a DXCore adapter to [**DisplayMonitor.DisplayAdapterId**](/uwp/api/windows.devices.display.displaymonitor.displayadapterid) information. To obtain an adapter's LUID, pass [**DXCoreAdapterProperty::InstanceLuid**](/windows/win32/dxcore/dxcore_interface/ne-dxcore_interface-dxcoreadapterproperty) to the [**IDXCoreAdapter::GetProperty**](/windows/win32/dxcore/dxcore_interface/nf-dxcore_interface-idxcoreadapter-getproperty) method.

## See also

* [Minimal DXCore application](dxcore-source-code.md)
* [DXCore Reference](/windows/win32/dxcore/dxcore-reference)
* [Direct3D 12 graphics](/windows/win32/direct3d12/direct3d-12-graphics)
