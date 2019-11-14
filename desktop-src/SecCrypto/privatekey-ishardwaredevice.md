---
Description: Returns a Boolean value that indicates whether the private key is stored in a hardware device.
ms.assetid: 9a06f598-55cd-441b-a85f-8bec299f8245
title: PrivateKey.IsHardwareDevice method
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- PrivateKey.IsHardwareDevice
api_type:
- COM
api_location:
- Capicom.dll
---

# PrivateKey.IsHardwareDevice method

\[The **IsHardwareDevice** method is available for use in the operating systems specified in the Requirements section. Instead, use the [**X509Certificate2.PrivateKey Property**](https://msdn.microsoft.com/library/ms148460(v=VS.90).aspx) in the [**System.Security.Cryptography.X509Certificates**](https://msdn.microsoft.com/library/73091bzx(v=VS.71).aspx) namespace.\]

The **IsHardwareDevice** method returns a Boolean value that indicates whether the private key is stored in a hardware device.

## Syntax


```VB
PrivateKey.IsHardwareDevice()
```



## Parameters

This method has no parameters.

## Return value

If true, the private key is stored in a hardware device.

## Remarks

The return value of this method is dependent on the [*cryptographic service provider*](https://msdn.microsoft.com/en-us/library/ms721572(v=VS.85).aspx) (CSP) used. This method will return a trustworthy value if a Microsoft CSP is used. If the CSP is not a Microsoft CSP, the return value cannot be trusted to be accurate.

## Requirements



|                            |                                                                                        |
|----------------------------|----------------------------------------------------------------------------------------|
| Redistributable<br/> | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>             | <dl> <dt>Capicom.dll</dt> </dl> |



## See also

<dl> <dt>

[**PrivateKey**](privatekey.md)
</dt> </dl>

 

 




