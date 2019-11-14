---
Description: Converts lowercase characters in a buffer to uppercase characters.
ms.assetid: 63293fda-6f55-419a-b5b4-7a3ada31580c
title: CharUpperBuffWrapW function
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- CharUpperBuffWrapW
api_type: 
- DllExport
api_location: 
- Shlwapi.dll
---

# CharUpperBuffWrapW function

\[**CharUpperBuffWrapW** is available for use in Windows XP. It may not be available in subsequent versions. You should use [**CharUpperBuffW**](https://msdn.microsoft.com/en-us/library/ms647475(v=VS.85).aspx) in its place.\]

Converts lowercase characters in a buffer to uppercase characters. The function converts the characters in place.

> [!Note]  
> **CharUpperBuffWrapW** is a wrapper for the **CharUpperBuffW** function. See the [**CharUpperBuff**](https://msdn.microsoft.com/en-us/library/ms647475(v=VS.85).aspx) page for further usage notes.

 

## Syntax


```C++
DWORD CharUpperBuffWrapW(
  _In_ LPWSTR pch,
  _In_ DWORD  cchLength
);
```



## Parameters

<dl> <dt>

*pch* \[in\]
</dt> <dd>

Type: **LPWSTR**

A pointer to a buffer that contains one or more Unicode characters to process.

</dd> <dt>

*cchLength* \[in\]
</dt> <dd>

Type: **DWORD**

Specifies the size, in characters, of the buffer pointed to by *pch*.

</dd> </dl>

## Return value

Type: **DWORD**

The number of characters processed.

## Remarks

The preferred method is to use [**CharUpperBuffW**](https://msdn.microsoft.com/en-us/library/ms647475(v=VS.85).aspx) in conjunction with the Microsoft Layer for Unicode (MSLU).

**CharUpperBuffWrapW** must be called directly from Shlwapi.dll, using ordinal 44.

## Requirements



|                                     |                                                                                                               |
|-------------------------------------|---------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional, Windows XP \[desktop apps only\]<br/>                                        |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                                          |
| DLL<br/>                      | <dl> <dt>Shlwapi.dll (version 5.0 or later)</dt> </dl> |



## See also

<dl> <dt>

[**CharUpperBuff**](https://msdn.microsoft.com/en-us/library/ms647475(v=VS.85).aspx)
</dt> </dl>

 

 




