---
Description: The StartService method puts the service in a &\#0034;start&\#0034; state.
ms.assetid: b2b38d64-b497-46f5-8638-a9a8ce50e888
ms.tgt_platform: multiple
title: StartService method of the CIM_BootService class
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- CIM_BootService.StartService
api_type: 
- COM
api_location: 
- CIMWin32.dll
---

# StartService method of the CIM\_BootService class

The **StartService** method puts the service in a "start" state. In a subclass, the set of possible return codes can be specified by using a **ValueMap** qualifier on the method. The strings to which the **ValueMap** contents are translated may also be specified in the subclass as a **Values** array qualifier. This method is inherited from [**CIM\_Service**](cim-service.md).

> [!IMPORTANT]
> The DMTF (Distributed Management Task Force) CIM (Common Information Model) classes are the parent classes upon which WMI classes are built. WMI currently supports only the [CIM 2.x version schemas](https://Go.Microsoft.Com/FWLink/p/?LinkID=309367).

 

This topic uses Managed Object Format (MOF) syntax. For more information about using this method see [Calling a Method](https://docs.microsoft.com/windows/desktop/WmiSdk/calling-a-method).

## Syntax


```mof
Integer StartService();
```



## Parameters

This method has no parameters.

## Return value

Returns a value of 0 (zero) on success, 1 (one) if the request is not supported, and any other number to indicate an error.

## Remarks

This method is currently not implemented by WMI. To use this method, you must implement it in your own provider.

This documentation is derived from the CIM class descriptions published by the DMTF. Microsoft may have made changes to correct minor errors, conform to Microsoft SDK documentation standards, or provide more information.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                          |
| Namespace<br/>                | Root\\CIMV2<br/>                                                                  |
| MOF<br/>                      | <dl> <dt>CIMWin32.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>CIMWin32.dll</dt> </dl> |



## See also

<dl> <dt>

[CIM\_BootService](startservice-method-in-class-cim-bootservice.md)
</dt> <dt>

[**CIM\_BootService**](cim-bootservice.md)
</dt> </dl>

 

 



