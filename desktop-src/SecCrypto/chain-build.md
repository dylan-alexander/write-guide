---
Description: Builds a certificate verification chain from an end certificate to the trusted root certificate and returns a Boolean value that indicates the overall validity of the chain.
ms.assetid: 878f09ba-d79b-4f14-b4f6-ecb54771f56f
title: IChain2::Build method
ms.topic: reference
ms.date: 05/31/2018
topic_type:
- APIRef
- kbSyntax
api_name:
- Chain.Build
- IChain2.Build
- IChain.Build
api_type:
- COM
api_location:
- Capicom.dll
---

# IChain2::Build method

\[CAPICOM is a 32-bit only component that is available for use in the following operating systems: Windows Server 2008, Windows Vista, and Windows XP. Instead, use the [**X509Chain Class**](https://msdn.microsoft.com/library/9bys9et1(v=VS.90).aspx) in the [**System.Security.Cryptography.X509Certificates**](https://msdn.microsoft.com/library/73091bzx(v=VS.71).aspx) namespace.\]

The **Build** method builds a certificate verification chain from an end certificate to the trusted [*root certificate*](https://msdn.microsoft.com/en-us/library/ms721604(v=VS.85).aspx) and returns a Boolean value that indicates the overall validity of the chain.

## Syntax


```VB
Chain.Build( _
  ByVal Certificate _
)
```



## Parameters

<dl> <dt>

*Certificate* \[in\]
</dt> <dd>

A [**Certificate**](certificate.md) object that represents the end certificate upon which the verification chain is to be built.

</dd> </dl>

## Return value

A Boolean value that indicates the overall validity of the chain. Overall validity is based on the validity checking policy in place.

## Remarks

The chain is built using the [**CertificateStatus.CheckFlag**](certificatestatus-checkflag.md) property as well as application and certificate policies specified by a [**CertificateStatus**](certificatestatus.md) object. The returned collection is ordered; the first certificate in the collection, **Certificates.Item**(1), is the end certificate of the chain. The last certificate in the collection, **Certificates.Item**(**Certificates.Count**), is the [*root certificate*](https://msdn.microsoft.com/en-us/library/ms721604(v=VS.85).aspx) of the chain. **Certificates.Item**(0) represents the entire chain.

Each time the **Chain.Build** method is called, the [*state*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) of the [**Chain**](chain.md) object is reset.

## Requirements



|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| End of client support<br/> | Windows Vista<br/>                                                               |
| End of server support<br/> | Windows Server 2008<br/>                                                         |
| Redistributable<br/>       | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>                   | <dl> <dt>Capicom.dll</dt> </dl> |



## See also

<dl> <dt>

[**Cryptography Objects**](cryptography-objects.md)
</dt> <dt>

[**Chain**](chain.md)
</dt> </dl>

 

 




