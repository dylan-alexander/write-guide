---
Description: The AddBefore method inserts an item before the specified position.
ms.assetid: ec10fd08-6bb9-4357-830c-78b3d3a32e03
title: CGenericList.AddBefore method (Wxlist.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- CGenericList.AddBefore
api_type: 
- COM
api_location: 
- Strmbase.lib
- Strmbase.dll
- Strmbasd.lib
- Strmbasd.dll
---

# CGenericList.AddBefore method

The `AddBefore` method inserts an item before the specified position.

## Syntax


```C++
POSITION AddBefore(
   POSITION p,
   OBJECT   *pObj
);
```



## Parameters

<dl> <dt>

*p* 
</dt> <dd>

Position before which to insert the list. If *p* is **NULL**, this method adds the item to the tail of the list.

</dd> <dt>

*pObj* 
</dt> <dd>

Pointer to an object of type **OBJECT** (the template type).

</dd> </dl>

## Return value

Returns the position indicator for the inserted item.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Wxlist.h (include Streams.h)</dt> </dl>                                                                                    |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CGenericList Class**](cgenericlist.md)
</dt> </dl>

 

 




