---
title: XInput and DirectInput
description: XInput is an API that allows applications to receive input from the Xbox Controller for Windows.
ms.assetid: 0f29a47b-24ed-c0fa-e9e9-8a061619845c
ms.topic: article
ms.date: 05/31/2018
---

# XInput and DirectInput

XInput is an API that allows applications to receive input from the Xbox Controller for Windows. This document describes the differences between XInput and [DirectInput](https://msdn.microsoft.com/en-us/library/Ee416842(v=VS.85).aspx) implementations of the Xbox Controller and how you can support XInput devices and legacy DirectInput devices at the same time.

> [!Note]  
> Use of legacy [DirectInput](https://msdn.microsoft.com/en-us/library/Ee416842(v=VS.85).aspx) is not recommended, and DirectInput is not available for Windows Store apps.

 

## The New Standard: XInput

XInput is now available for game development. This is the new input standard for both the Xbox and Windows. The APIs are available through the DirectX SDK, and the driver is available through Windows Update.

There are several advantages to using XInput over [DirectInput](https://msdn.microsoft.com/en-us/library/Ee416842(v=VS.85).aspx):

-   XInput is easier to use and requires less setup than [DirectInput](https://msdn.microsoft.com/en-us/library/Ee416842(v=VS.85).aspx)
-   Both Xbox and Windows programming will use the same sets of core APIs, allowing programming to translate cross-platform much easier
-   There will be a large installed base of Xbox controllers
-   XInput devices (that is, the Xbox controllers) will have vibration functionality only when using XInput APIs
-   Future controllers released for the Xbox console (that is, steering wheels) will also work on Windows

### Using the Xbox Controller with DirectInput

The Xbox Controller is properly enumerated on [DirectInput](https://msdn.microsoft.com/en-us/library/Ee416842(v=VS.85).aspx), and can be used with the DirectInputAPIs. However, some functionality provided by XInput will be missing from the DirectInput implementation:

-   The left and right trigger buttons will act as a single button, not independently
-   The vibration effects will not be available
-   Querying for headset devices will not be available

The combination of the left and right triggers in [DirectInput](https://msdn.microsoft.com/en-us/library/Ee416842(v=VS.85).aspx) is by design. Games have always assumed that DirectInput device axes are centered when there is no user interaction with the device. However, the Xbox controller was designed to register minimum value, not center, when the triggers are not being held. Older games would therefore assume user interaction.

The solution was to combine the triggers, setting one trigger to a positive direction and the other to a negative direction, so no user interaction is indicative to [DirectInput](https://msdn.microsoft.com/en-us/library/Ee416842(v=VS.85).aspx) of the "control" being at center.

In order to test the trigger values separately, you must use XInput.

## XInput and DirectInput Side by Side

By supporting XInput only, your game will not work with legacy [DirectInput](https://msdn.microsoft.com/en-us/library/Ee416842(v=VS.85).aspx) devices. XInput will not recognize these devices.

If you want your game to support legacy [DirectInput](https://msdn.microsoft.com/en-us/library/Ee416842(v=VS.85).aspx) devices, you may use DirectInput and XInput side by side. When enumerating your DirectInput devices, all DirectInput devices will enumerate correctly. All XInput devices will show up as both XInput and DirectInput devices, but they should not be handled through DirectInput. You will need to determine which of your DirectInput devices are legacy devices, and which are XInput devices, and remove them from the enumeration of DirectInput devices.

To do this, insert this code into your DirectInput enumeration callback:


```
#include <wbemidl.h>
#include <oleauto.h>
#include <wmsstd.h>

//-----------------------------------------------------------------------------
// Enum each PNP device using WMI and check each device ID to see if it contains 
// "IG_" (ex. "VID_045E&PID_028E&IG_00").  If it does, then it's an XInput device
// Unfortunately this information can not be found by just using DirectInput 
//-----------------------------------------------------------------------------
BOOL IsXInputDevice( const GUID* pGuidProductFromDirectInput )
{
    IWbemLocator*           pIWbemLocator  = NULL;
    IEnumWbemClassObject*   pEnumDevices   = NULL;
    IWbemClassObject*       pDevices[20]   = {0};
    IWbemServices*          pIWbemServices = NULL;
    BSTR                    bstrNamespace  = NULL;
    BSTR                    bstrDeviceID   = NULL;
    BSTR                    bstrClassName  = NULL;
    DWORD                   uReturned      = 0;
    bool                    bIsXinputDevice= false;
    UINT                    iDevice        = 0;
    VARIANT                 var;
    HRESULT                 hr;

    // CoInit if needed
    hr = CoInitialize(NULL);
    bool bCleanupCOM = SUCCEEDED(hr);

    // Create WMI
    hr = CoCreateInstance( __uuidof(WbemLocator),
                           NULL,
                           CLSCTX_INPROC_SERVER,
                           __uuidof(IWbemLocator),
                           (LPVOID*) &pIWbemLocator);
    if( FAILED(hr) || pIWbemLocator == NULL )
        goto LCleanup;

    bstrNamespace = SysAllocString( L"\\\\.\\root\\cimv2" );if( bstrNamespace == NULL ) goto LCleanup;        
    bstrClassName = SysAllocString( L"Win32_PNPEntity" );   if( bstrClassName == NULL ) goto LCleanup;        
    bstrDeviceID  = SysAllocString( L"DeviceID" );          if( bstrDeviceID == NULL )  goto LCleanup;        
    
    // Connect to WMI 
    hr = pIWbemLocator->ConnectServer( bstrNamespace, NULL, NULL, 0L, 
                                       0L, NULL, NULL, &pIWbemServices );
    if( FAILED(hr) || pIWbemServices == NULL )
        goto LCleanup;

    // Switch security level to IMPERSONATE. 
    CoSetProxyBlanket( pIWbemServices, RPC_C_AUTHN_WINNT, RPC_C_AUTHZ_NONE, NULL, 
                       RPC_C_AUTHN_LEVEL_CALL, RPC_C_IMP_LEVEL_IMPERSONATE, NULL, EOAC_NONE );                    

    hr = pIWbemServices->CreateInstanceEnum( bstrClassName, 0, NULL, &pEnumDevices ); 
    if( FAILED(hr) || pEnumDevices == NULL )
        goto LCleanup;

    // Loop over all devices
    for( ;; )
    {
        // Get 20 at a time
        hr = pEnumDevices->Next( 10000, 20, pDevices, &uReturned );
        if( FAILED(hr) )
            goto LCleanup;
        if( uReturned == 0 )
            break;

        for( iDevice=0; iDevice<uReturned; iDevice++ )
        {
            // For each device, get its device ID
            hr = pDevices[iDevice]->Get( bstrDeviceID, 0L, &var, NULL, NULL );
            if( SUCCEEDED( hr ) && var.vt == VT_BSTR && var.bstrVal != NULL )
            {
                // Check if the device ID contains "IG_".  If it does, then it's an XInput device
                    // This information can not be found from DirectInput 
                if( wcsstr( var.bstrVal, L"IG_" ) )
                {
                    // If it does, then get the VID/PID from var.bstrVal
                    DWORD dwPid = 0, dwVid = 0;
                    WCHAR* strVid = wcsstr( var.bstrVal, L"VID_" );
                    if( strVid && swscanf( strVid, L"VID_%4X", &dwVid ) != 1 )
                        dwVid = 0;
                    WCHAR* strPid = wcsstr( var.bstrVal, L"PID_" );
                    if( strPid && swscanf( strPid, L"PID_%4X", &dwPid ) != 1 )
                        dwPid = 0;

                    // Compare the VID/PID to the DInput device
                    DWORD dwVidPid = MAKELONG( dwVid, dwPid );
                    if( dwVidPid == pGuidProductFromDirectInput->Data1 )
                    {
                        bIsXinputDevice = true;
                        goto LCleanup;
                    }
                }
            }   
            SAFE_RELEASE( pDevices[iDevice] );
        }
    }

LCleanup:
    if(bstrNamespace)
        SysFreeString(bstrNamespace);
    if(bstrDeviceID)
        SysFreeString(bstrDeviceID);
    if(bstrClassName)
        SysFreeString(bstrClassName);
    for( iDevice=0; iDevice<20; iDevice++ )
        SAFE_RELEASE( pDevices[iDevice] );
    SAFE_RELEASE( pEnumDevices );
    SAFE_RELEASE( pIWbemLocator );
    SAFE_RELEASE( pIWbemServices );

    if( bCleanupCOM )
        CoUninitialize();

    return bIsXinputDevice;
}


//-----------------------------------------------------------------------------
// Name: EnumJoysticksCallback()
// Desc: Called once for each enumerated joystick. If we find one, create a
//       device interface on it so we can play with it.
//-----------------------------------------------------------------------------
BOOL CALLBACK EnumJoysticksCallback( const DIDEVICEINSTANCE* pdidInstance,
                                     VOID* pContext )
{
    HRESULT hr;

    if( IsXInputDevice( &pdidInstance->guidProduct ) )
        return DIENUM_CONTINUE;

     // Device is verified not XInput, so add it to the list of DInput devices

     return DIENUM_CONTINUE;    
}
```



## Related topics

<dl> <dt>

[Getting Started With XInput](getting-started-with-xinput.md)
</dt> <dt>

[Programming Reference](programming-reference.md)
</dt> </dl>

 

 




