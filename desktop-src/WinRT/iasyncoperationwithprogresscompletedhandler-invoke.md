---
Description: Invokes the method that is called when the specified asynchronous operation reports progress.
ms.assetid: FB60DDC0-7521-4999-8DD8-175556004198
title: IAsyncOperationWithProgressCompletedHandler<TResult,TProgress>::Invoke method
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- IAsyncOperationWithProgressCompletedHandler<TResult,TProgress>.Invoke
api_type: 
- COM
api_location: 
---

# IAsyncOperationWithProgressCompletedHandler<TResult,TProgress>::Invoke method

Invokes the method that is called when the specified asynchronous operation reports progress.

## Syntax


```C++
HRESULT Invoke(
  [in] IAsyncOperationWithProgress<TResult,TProgress> *asyncInfo
);
```



## Parameters

<dl> <dt>

*asyncInfo* \[in\]
</dt> <dd>

Type: **[**IAsyncOperationWithProgress<TResult,TProgress>**](https://msdn.microsoft.com/en-us/library/BR205807(v=VS.85).aspx)\***

The asynchronous action that reports completion.

</dd> </dl>

## Return value

Type: **HRESULT**

If this method succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Requirements



|                                     |                                |
|-------------------------------------|--------------------------------|
| Minimum supported client<br/> | Windows 8<br/>           |
| Minimum supported server<br/> | Windows Server 2012<br/> |



## See also

<dl> <dt>

[**IAsyncOperationWithProgressCompletedHandler<TResult,TProgress>**](https://msdn.microsoft.com/en-us/library/BR205808(v=VS.85).aspx)
</dt> </dl>

 

 




