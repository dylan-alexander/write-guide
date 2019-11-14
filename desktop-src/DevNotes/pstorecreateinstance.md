---
Description: Retrieves an interface pointer to a storage provider.
ms.assetid: 22b5b003-82fa-48f1-96db-a8d6dd70d6d1
title: PStoreCreateInstance function (Pstore.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- PStoreCreateInstance
api_type: 
- DllExport
api_location: 
- Pstorec.dll
---

# PStoreCreateInstance function

\[Protected Storage (Pstore) is available for use in Windows Server 2003 and Windows XP. It is only available for read-only operations in Windows Server 2008 and Windows Vista, but may be unavailable in subsequent versions. Pstore uses an older implementation of data protection. Developers are strongly encouraged to take advantage of the stronger data protection provided by the [**CryptProtectData**](https://msdn.microsoft.com/en-us/library/Aa380261(v=VS.85).aspx) and [**CryptUnprotectData**](https://msdn.microsoft.com/en-us/library/Aa380882(v=VS.85).aspx) functions.\]

\[This function may be altered or unavailable in future versions of Windows. Use the **CryptProtectData** and **CryptUnprotectData** functions instead of this function.\]

Retrieves an interface pointer to a storage provider.

## Syntax


```C++
HRESULT __stdcall PStoreCreateInstance(
  _Out_ IPStore        **ppProvider,
  _In_  PST_PROVIDERID *pProviderID,
  _In_  void           *pReserved,
  _In_  DWORD          dwFlags
);
```



## Parameters

<dl> <dt>

*ppProvider* \[out\]
</dt> <dd>

A pointer to the retrieved interface pointer for the storage provider. When you finish using the interface, decrement its reference count by calling its [**IUnknown::Release**](https://msdn.microsoft.com/en-us/library/ms682317(v=VS.85).aspx) method. This parameter cannot be **NULL**.

</dd> <dt>

*pProviderID* \[in\]
</dt> <dd>

A pointer to the **GUID** that identifies the storage provider. If this parameter is **NULL**, then the base storage provider is used.

</dd> <dt>

*pReserved* \[in\]
</dt> <dd>

Reserved; must be **NULL**.

</dd> <dt>

*dwFlags* \[in\]
</dt> <dd>

Reserved; must be zero.

</dd> </dl>

## Return value

The return value is an **HRESULT**. A value of **S\_OK** indicates the function was successful.

## Remarks

This function has no associated import library; you must call it using the [**LoadLibrary**](https://msdn.microsoft.com/en-us/library/ms684175(v=VS.85).aspx) and [**GetProcAddress**](https://msdn.microsoft.com/en-us/library/ms683212(v=VS.85).aspx) functions.

## Requirements



|                   |                                                                                        |
|-------------------|----------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>Pstore.h</dt> </dl>    |
| DLL<br/>    | <dl> <dt>Pstorec.dll</dt> </dl> |



## See also

<dl> <dt>

[**CryptProtectData**](https://msdn.microsoft.com/en-us/library/Aa380261(v=VS.85).aspx)
</dt> <dt>

[**CryptUnprotectData**](https://msdn.microsoft.com/en-us/library/Aa380882(v=VS.85).aspx)
</dt> </dl>

 

 




