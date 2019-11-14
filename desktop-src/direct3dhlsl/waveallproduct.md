---
title: WaveActiveProduct function
description: Multiplies the values of the expression together across all active lanes in the current wave and replicates it back to all active lanes.
ms.assetid: B259244D-C993-4F4A-AF09-F077D99AD025
keywords:
- WaveAllProduct function HLSL
topic_type:
- apiref
api_name:
- WaveAllProduct
api_type:
- NA
ms.topic: reference
ms.date: 05/31/2018
api_location: 
---

# WaveActiveProduct function

Multiplies the values of the expression together across all active lanes in the current wave and replicates it back to all active lanes.

## Syntax

``` syntax
<type> WaveAllProduct(
   <type> expr
);
```

## Parameters

<dl> <dt>

*expr* 
</dt> <dd>

The expression to evaluate.

</dd> </dl>

## Return value

The product value.

## Remarks

The order of operations is undefined.

This function is supported from shader model 6.0, in the following types of shaders:



| Vertex | Hull | Domain | Geometry | Pixel | Compute |
|--------|------|--------|----------|-------|---------|
|        |      |        |          | x     | x       |



 

## See also

<dl> <dt>

[Overview of Shader Model 6](hlsl-shader-model-6-0-features-for-direct3d-12.md)
</dt> <dt>

[Shader Model 6](shader-model-6-0.md)
</dt> </dl>

 

 




