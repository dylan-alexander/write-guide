---
Description: The installer sets the VersionNT64 property to the version number for the operating system only if the system is running on a 64-bit computer.
ms.assetid: 190f8251-a377-4490-9de9-98d149185865
title: VersionNT64 property
ms.topic: reference
ms.date: 05/31/2018
---

# VersionNT64 property

The installer sets the **VersionNT64** property to the version number for the operating system only if the system is running on a 64-bit computer. The property is undefined if the operating system is not 64-bit.

The value is an integer: MajorVersion \* 100 + MinorVersion.

For compatibility reasons, the property is also undefined if the [**Template Summary**](template-summary.md) property indicates the package is for 32-bit Intel systems and the operating system is a 64-bit architecture that is not Intel64 or x64 (such as ARM64).

## Remarks

Conditional expressions test for 64-bit Windows simply by using the property name, or by verifying the version using a comparison operator.

## Requirements



|                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Version<br/> | Windows Installer 5.0 on Windows Server 2012, Windows 8, Windows Server 2008 R2 or Windows 7. Windows Installer 4.0 or Windows Installer 4.5 on Windows Server 2008 or Windows Vista. Windows Installer on Windows Server 2003 or Windows XP See the [Windows Installer Run-Time Requirements](windows-installer-portal.md) for information about the minimum Windows service pack that is required by a Windows Installer version.<br/> |



## See also

<dl> <dt>

[Properties](properties.md)
</dt> </dl>

 

 




