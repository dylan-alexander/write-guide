---
title: max
description: Selects the greater of x and y.
ms.assetid: 08e17a0c-6d44-49ea-b613-bd262534522c
keywords:
- max HLSL
topic_type:
- apiref
api_name:
- max
api_type:
- NA
ms.topic: reference
ms.date: 05/31/2018
api_location: 
---

# max

Selects the greater of x and y.



| ret max(x, y) |
|---------------|



 

## Parameters



| Item                                                   | Description                          |
|--------------------------------------------------------|--------------------------------------|
| <span id="x"></span><span id="X"></span>*x*<br/> | \[in\] The x input value.<br/> |
| <span id="y"></span><span id="Y"></span>*y*<br/> | \[in\] The y input value.<br/> |



 

## Return Value

The *x* or *y* parameter, whichever is the largest value.

## Remarks

For values of -INF or INF, max will behave as expected. However for values of NaN, the results are undefined.

## Type Description



| Name | In/Out      | [**Template Type**](dx-graphics-hlsl-intrinsic-functions.md)                                                  | [**Component Type**](dx-graphics-hlsl-intrinsic-functions.md)                 | Size                         |
|------|-------------|----------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|------------------------------|
| x    | in          | [**scalar**](dx-graphics-hlsl-intrinsic-functions.md), **vector**, or **matrix** | [**float**](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types), [**int**](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types) | any                          |
| y    | in          | same as input x                                                                                                | [**float**](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types), [**int**](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types) | same dimension(s) as input x |
| ret  | return type | same as input x                                                                                                | [**float**](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types), [**int**](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types) | same dimension(s) as input x |



 

## Minimum Shader Model

This function is supported in the following shader models.



| Shader Model                                                                       | Supported                   |
|------------------------------------------------------------------------------------|-----------------------------|
| [Shader Model 2 (DirectX HLSL)](dx-graphics-hlsl-sm2.md) and higher shader models | yes                         |
| [Shader Model 1 (DirectX HLSL)](dx-graphics-hlsl-sm1.md)                          | yes (vs\_1\_1 and ps\_1\_4) |



 

## See also

<dl> <dt>

[**Intrinsic Functions (DirectX HLSL)**](dx-graphics-hlsl-intrinsic-functions.md)
</dt> </dl>

 

 





