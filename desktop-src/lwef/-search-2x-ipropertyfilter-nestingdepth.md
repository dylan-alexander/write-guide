---
title: IPropertyFilter NestingDepth property (WdsSharedIDL.h)
description: Filters depth within a nested set of parentheses.
ms.assetid: a52992b3-d232-46a5-907c-8df6bd5ad6fc
keywords:
- NestingDepth property Legacy Windows Environment Features
- NestingDepth property Legacy Windows Environment Features , IPropertyFilter interface
- IPropertyFilter interface Legacy Windows Environment Features , NestingDepth property
topic_type:
- apiref
api_name:
- IPropertyFilter.NestingDepth
- IPropertyFilter.get_NestingDepth
- IPropertyFilter.put_NestingDepth
api_location:
- WdsSharedIDL.h
api_type:
- COM
ms.topic: reference
ms.date: 05/31/2018
---

# IPropertyFilter::NestingDepth property

\[Windows Search 2.x is available for use in the operating system specified in the Requirements section. It might be altered or unavailable in later versions. Use the [Windows Search API](https://docs.microsoft.com/windows/desktop/search/-search-reference-entry-page) instead.\]

Filters depth within a nested set of parentheses.

This property is read/write.

## Syntax


```C++
HRESULT put_NestingDepth(
  [in]          long depth
);

HRESULT get_NestingDepth(
  [out, retval] long *depth
);
```



## Property value

Sets the number indicating the depth of nested parentheses.

## Requirements



|                                     |                                                                                           |
|-------------------------------------|-------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP with SP2 \[desktop apps only\]<br/>                                      |
| Minimum supported server<br/> | Windows Server 2003 with SP1 \[desktop apps only\]<br/>                             |
| Redistributable<br/>          | Windows Desktop Search (WDS) 2.6.5<br/>                                             |
| Header<br/>                   | <dl> <dt>WdsSharedIDL.h</dt> </dl> |



 

 





