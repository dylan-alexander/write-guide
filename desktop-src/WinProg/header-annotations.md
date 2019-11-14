---
title: Header Annotations
description: Header annotations describe how a function uses its parameters and return value.
ms.assetid: 4f9e42b1-2fe4-4173-946e-ab1805a96b9e
keywords:
- Windows API, header file annotations
- header file annotations
- Specstrings.h
- standard annotation language (SAL)
- _bcount
- _deref
- _deref_opt
- _ecount
- _full
- _in
- _inout
- _opt
- _out
- _part
ms.topic: article
ms.date: 05/31/2018
---

# Header Annotations

\[This topic describes the annotations supported in the Windows headers through Windows 7. If you are developing for Windows 8, you should use the annotations described in [SAL Annotations]( https://go.microsoft.com/fwlink/p/?linkid=247283).\]\]

Header annotations describe how a function uses its parameters and return value. These annotations have been added to many of the Windows header files to help you ensure that you are calling the Windows API correctly. If you enable code analysis, which is available starting with the Visual Studio 2005, the compiler will produce level 6000 warnings if you are not calling these functions per the usage described through the annotations. You can also add these annotations in your own code to ensure that it is being called correctly. To enable code analysis in Visual Studio, see the documentation for your version of Visual Studio.

These annotations are defined in Specstrings.h. They are built on primitives that are part of the Standard Annotation Language (SAL) and implemented using `_declspec("SAL_*")`.

There are two classes of annotations: buffer annotations and advanced annotations.

## Buffer Annotations

Buffer annotations describe how functions use their pointers and can be used to detect buffer overruns. Each parameter may use zero or one buffer annotation. A buffer annotation is constructed with a leading underscore and the components described in the following sections.



| Buffer size                                                                                  | Description                                                                                                                                                                             |
|----------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span id="_size_"></span><span id="_SIZE_"></span>(*size*)<br/>                        | Specifies the total size of the buffer. Use with \_bcount and \_ecount; do not use with \_part. This value is the accessible space; it may be less than the allocated space.<br/> |
| <span id="_size_length_"></span><span id="_SIZE_LENGTH_"></span>(*size*,*length*)<br/> | Specifies the total size and initialized length of the buffer. Use with \_bcount\_part and \_ecount\_part. The total size may be less than the allocated space.<br/>              |



 



| Buffer size units                                                       | Description                                |
|-------------------------------------------------------------------------|--------------------------------------------|
| <span id="_bcount"></span><span id="_BCOUNT"></span>\_bcount<br/> | The buffer size is in bytes.<br/>    |
| <span id="_ecount"></span><span id="_ECOUNT"></span>\_ecount<br/> | The buffer size is in elements.<br/> |



 



| Direction                                                            | Description                                                                                                                                                                                                                |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span id="_in"></span><span id="_IN"></span>\_in<br/>          | The function reads from the buffer. The caller provides the buffer and initializes it.<br/>                                                                                                                          |
| <span id="_inout"></span><span id="_INOUT"></span>\_inout<br/> | The function both reads from and writes to buffer. The caller provides the buffer and initializes it. If used with \_deref, the buffer may be reallocated by the function.<br/>                                      |
| <span id="_out"></span><span id="_OUT"></span>\_out<br/>       | The function writes to the buffer. If used on the return value or with \_deref, the function provides the buffer and initializes it. Otherwise, the caller provides the buffer and the function initializes it.<br/> |



 



| Indirection                                                                       | Description                                                                                            |
|-----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| <span id="_deref"></span><span id="_DEREF"></span>\_deref<br/>              | Dereference the parameter to obtain the buffer pointer. This parameter may not be **NULL**.<br/> |
| <span id="_deref_opt"></span><span id="_DEREF_OPT"></span>\_deref\_opt<br/> | Dereference the parameter to obtain the buffer pointer. This parameter can be **NULL**.<br/>     |



 



| Initialization                                                    | Description                                                                                                              |
|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| <span id="_full"></span><span id="_FULL"></span>\_full<br/> | The function initializes the entire buffer. Use only with output buffers.<br/>                                     |
| <span id="_part"></span><span id="_PART"></span>\_part<br/> | The function initializes part of the buffer, and explicitly indicates how much. Use only with output buffers.<br/> |



 



| Required or optional buffer                                    | Description                                |
|----------------------------------------------------------------|--------------------------------------------|
| <span id="_opt"></span><span id="_OPT"></span>\_opt<br/> | This parameter can be **NULL**.<br/> |



 

The following example shows the annotations for the **GetModuleFileName** function. The *hModule* parameter is an optional input parameter . The *lpFilename* parameter is an output parameter; its size in characters is specified by the *nSize* parameter and its length includes the **null**-terminating character. The *nSize* parameter is an input parameter.


```C++
DWORD
WINAPI
GetModuleFileName(
    __in_opt HMODULE hModule,
    __out_ecount_part(nSize, return + 1) LPTSTR lpFilename,
    __in DWORD nSize
    );
```



The following are the annotations defined in Specstrings.h. Use the information in the tables above to interpret their meaning.

<dl> \_\_bcount(*size*)  
\_\_bcount\_opt(*size*)  
\_\_deref\_bcount(*size*)  
\_\_deref\_bcount\_opt(*size*)  
\_\_deref\_ecount(*size*)  
\_\_deref\_ecount\_opt(*size*)  
\_\_deref\_in  
\_\_deref\_in\_bcount(*size*)  
\_\_deref\_in\_bcount\_opt(*size*)  
\_\_deref\_in\_ecount(*size*)  
\_\_deref\_in\_ecount\_opt(*size*)  
\_\_deref\_in\_opt  
\_\_deref\_inout  
\_\_deref\_inout\_bcount(*size*)  
\_\_deref\_inout\_bcount\_full(*size*)  
\_\_deref\_inout\_bcount\_full\_opt(*size*)  
\_\_deref\_inout\_bcount\_opt(*size*)  
\_\_deref\_inout\_bcount\_part(*size*,*length*)  
\_\_deref\_inout\_bcount\_part\_opt(*size*,*length*)  
\_\_deref\_inout\_ecount(*size*)  
\_\_deref\_inout\_ecount\_full(*size*)  
\_\_deref\_inout\_ecount\_full\_opt(*size*)  
\_\_deref\_inout\_ecount\_opt(*size*)  
\_\_deref\_inout\_ecount\_part(*size*,*length*)  
\_\_deref\_inout\_ecount\_part\_opt(*size*,*length*)  
\_\_deref\_inout\_opt  
\_\_deref\_opt\_bcount(*size*)  
\_\_deref\_opt\_bcount\_opt(*size*)  
\_\_deref\_opt\_ecount(*size*)  
\_\_deref\_opt\_ecount\_opt(*size*)  
\_\_deref\_opt\_in  
\_\_deref\_opt\_in\_bcount(*size*)  
\_\_deref\_opt\_in\_bcount\_opt(*size*)  
\_\_deref\_opt\_in\_ecount(*size*)  
\_\_deref\_opt\_in\_ecount\_opt(*size*)  
\_\_deref\_opt\_in\_opt  
\_\_deref\_opt\_inout  
\_\_deref\_opt\_inout\_bcount(*size*)  
\_\_deref\_opt\_inout\_bcount\_full(*size*)  
\_\_deref\_opt\_inout\_bcount\_full\_opt(*size*)  
\_\_deref\_opt\_inout\_bcount\_opt(*size*)  
\_\_deref\_opt\_inout\_bcount\_part(*size*,*length*)  
\_\_deref\_opt\_inout\_bcount\_part\_opt(*size*,*length*)  
\_\_deref\_opt\_inout\_ecount(*size*)  
\_\_deref\_opt\_inout\_ecount\_full(*size*)  
\_\_deref\_opt\_inout\_ecount\_full\_opt(*size*)  
\_\_deref\_opt\_inout\_ecount\_opt(*size*)  
\_\_deref\_opt\_inout\_ecount\_part(*size*,*length*)  
\_\_deref\_opt\_inout\_ecount\_part\_opt(*size*,*length*)  
\_\_deref\_opt\_inout\_opt  
\_\_deref\_opt\_out  
\_\_deref\_opt\_out\_bcount(*size*)  
\_\_deref\_opt\_out\_bcount\_full(*size*)  
\_\_deref\_opt\_out\_bcount\_full\_opt(*size*)  
\_\_deref\_opt\_out\_bcount\_opt(*size*)  
\_\_deref\_opt\_out\_bcount\_part(*size*,*length*)  
\_\_deref\_opt\_out\_bcount\_part\_opt(*size*,*length*)  
\_\_deref\_opt\_out\_ecount(*size*)  
\_\_deref\_opt\_out\_ecount\_full(*size*)  
\_\_deref\_opt\_out\_ecount\_full\_opt(*size*)  
\_\_deref\_opt\_out\_ecount\_opt(*size*)  
\_\_deref\_opt\_out\_ecount\_part(*size*,*length*)  
\_\_deref\_opt\_out\_ecount\_part\_opt(*size*,*length*)  
\_\_deref\_opt\_out\_opt  
\_\_deref\_out  
\_\_deref\_out\_bcount(*size*)  
\_\_deref\_out\_bcount\_full(*size*)  
\_\_deref\_out\_bcount\_full\_opt(*size*)  
\_\_deref\_out\_bcount\_opt(*size*)  
\_\_deref\_out\_bcount\_part(*size*,*length*)  
\_\_deref\_out\_bcount\_part\_opt(*size*,*length*)  
\_\_deref\_out\_ecount(*size*)  
\_\_deref\_out\_ecount\_full(*size*)  
\_\_deref\_out\_ecount\_full\_opt(*size*)  
\_\_deref\_out\_ecount\_opt(*size*)  
\_\_deref\_out\_ecount\_part(*size*,*length*)  
\_\_deref\_out\_ecount\_part\_opt(*size*,*length*)  
\_\_deref\_out\_opt  
\_\_ecount(*size*)  
\_\_ecount\_opt(*size*)  
\_\_in  
\_\_in\_bcount(*size*)  
\_\_in\_bcount\_opt(*size*)  
\_\_in\_ecount(*size*)  
\_\_in\_ecount\_opt(*size*)  
\_\_in\_opt  
\_\_inout  
\_\_inout\_bcount(*size*)  
\_\_inout\_bcount\_full(*size*)  
\_\_inout\_bcount\_full\_opt(*size*)  
\_\_inout\_bcount\_opt(*size*)  
\_\_inout\_bcount\_part(*size*,*length*)  
\_\_inout\_bcount\_part\_opt(*size*,*length*)  
\_\_inout\_ecount(*size*)  
\_\_inout\_ecount\_full(*size*)  
\_\_inout\_ecount\_full\_opt(*size*)  
\_\_inout\_ecount\_opt(*size*)  
\_\_inout\_ecount\_part(*size*,*length*)  
\_\_inout\_ecount\_part\_opt(*size*,*length*)  
\_\_inout\_opt  
\_\_out  
\_\_out\_bcount(*size*)  
\_\_out\_bcount\_full(*size*)  
\_\_out\_bcount\_full\_opt(*size*)  
\_\_out\_bcount\_opt(*size*)  
\_\_out\_bcount\_part(*size*,*length*)  
\_\_out\_bcount\_part\_opt(*size*,*length*)  
\_\_out\_ecount(*size*)  
\_\_out\_ecount\_full(*size*)  
\_\_out\_ecount\_full\_opt(*size*)  
\_\_out\_ecount\_opt(*size*)  
\_\_out\_ecount\_part(*size*,*length*)  
\_\_out\_ecount\_part\_opt(*size*,*length*)  
\_\_out\_opt  
</dl>

## Advanced Annotations

Advanced annotations provide additional information about the parameter or return value. Each parameter or return value may use zero or one advanced annotation.



| Annotation                                                                                                                                               | Description                                                                                                                                                                                                                                                                     |
|----------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span id="__blocksOn_resource_"></span><span id="__blockson_resource_"></span><span id="__BLOCKSON_RESOURCE_"></span>\_\_blocksOn(*resource*)<br/> | The functions blocks on the specified resource.<br/>                                                                                                                                                                                                                      |
| <span id="__callback"></span><span id="__CALLBACK"></span>\_\_callback<br/>                                                                        | The function can be used as a function pointer.<br/>                                                                                                                                                                                                                      |
| <span id="__checkReturn"></span><span id="__checkreturn"></span><span id="__CHECKRETURN"></span>\_\_checkReturn<br/>                               | Callers must check the return value.<br/>                                                                                                                                                                                                                                 |
| <span id="__format_string"></span><span id="__FORMAT_STRING"></span>\_\_format\_string<br/>                                                        | The parameter is a string that contains printf-style % markers.<br/>                                                                                                                                                                                                      |
| <span id="__in_awcount_expr_size_"></span><span id="__IN_AWCOUNT_EXPR_SIZE_"></span>\_\_in\_awcount(*expr*,*size*)<br/>                            | If the expression is true at exit, the size of the input buffer is specified in bytes. If the expression is false, the size is specified in elements.<br/>                                                                                                                |
| <span id="__nullnullterminated"></span><span id="__NULLNULLTERMINATED"></span>\_\_nullnullterminated<br/>                                          | The buffer may be accessed up to and including the first sequence of two **null** characters or pointers.<br/>                                                                                                                                                            |
| <span id="__nullterminated"></span><span id="__NULLTERMINATED"></span>\_\_nullterminated<br/>                                                      | The buffer may be accessed up to and including the first **null** character or pointer.<br/>                                                                                                                                                                              |
| <span id="__out_awcount_expr_size_"></span><span id="__OUT_AWCOUNT_EXPR_SIZE_"></span>\_\_out\_awcount(*expr*,*size*)<br/>                         | If the expression is true at exit, the size of the output buffer is specified in bytes. If the expression is false, the size is specified in elements. <br/>                                                                                                              |
| <span id="__override"></span><span id="__OVERRIDE"></span>\_\_override<br/>                                                                        | Specifies C#-style override behavior for virtual methods.<br/>                                                                                                                                                                                                           |
| <span id="__reserved"></span><span id="__RESERVED"></span>\_\_reserved<br/>                                                                        | The parameter is reserved for future use and must be zero or **NULL**.<br/>                                                                                                                                                                                               |
| <span id="__success_expr_"></span><span id="__SUCCESS_EXPR_"></span>\_\_success(*expr*)<br/>                                                       | If the expression is true at exit, the caller can rely on all guarantees specified by other annotations. If the expression is false, the caller cannot rely on the guarantees. This annotation is automatically added to functions that return an **HRESULT** value.<br/> |
| <span id="__typefix_ctype_"></span><span id="__TYPEFIX_CTYPE_"></span>\_\_typefix(*ctype*)<br/>                                                    | Treat the parameter as the specified type rather than its declared type.<br/>                                                                                                                                                                                             |



 

The following examples show the buffer and advanced annotations for the [**DeleteTimerQueueTimer**](https://docs.microsoft.com/windows/desktop/api/threadpoollegacyapiset/nf-threadpoollegacyapiset-deletetimerqueuetimer), [**FreeEnvironmentStrings**](https://docs.microsoft.com/windows/desktop/api/processenv/nf-processenv-freeenvironmentstringsa), and [**UnhandledExceptionFilter**](https://docs.microsoft.com/windows/desktop/api/errhandlingapi/nf-errhandlingapi-unhandledexceptionfilter) functions.


```C++
__checkReturn
BOOL
WINAPI
DeleteTimerQueueTimer(
    __in_opt HANDLE TimerQueue,
    __in     HANDLE Timer,
    __in_opt HANDLE CompletionEvent
    );

BOOL
WINAPI
FreeEnvironmentStrings(
    __in __nullnullterminated LPTCH
    );

__callback
LONG
WINAPI
UnhandledExceptionFilter(
    __in struct _EXCEPTION_POINTERS *ExceptionInfo
    );

```



## Related topics

<dl> <dt>

[SAL Annotations](https://go.microsoft.com/fwlink/p/?linkid=101212)
</dt> <dt>

[Walkthrough: Analyzing C/C++ Code for Defects](https://go.microsoft.com/fwlink/p/?linkid=101213)
</dt> </dl>

 

 





