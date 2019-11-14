---
Description: The <name> element specifies the name of this library. This element is required and has no attributes or child elements.
ms.assetid: 1F433405-5943-4579-BDAD-423C4E1A6E76
title: name Element (Library Schema)
ms.topic: article
ms.date: 05/31/2018
---

# name Element (Library Schema)

The <name> element specifies the name of this library. This element is required and has no attributes or child elements.

## Syntax

``` syntax
<!-- name -->
<xs:element name="libraryDescription">
    <xs:complexType>
        <xs:all>
            <xs:element name="name" type="xs:string"/>
...
</libraryDescription>
```

## Element Information



| Parent Element                                                               | Child Elements |
|------------------------------------------------------------------------------|----------------|
| [libraryDescription Element (Library Schema)](schema-librarydescription.md) |                |



 

## Remarks

The name is the friendly library name that is displayed in Windows Explorer. The name can be specified in a <dllname>,<index> format, as in the following example.


```
<?xml version="1.0" encoding="UTF-8"?>
<libraryDescription xmlns="https://schemas.microsoft.com/windows/2009/library">
  <name>@shell32.dll,-34575</name>
...
</libraryDescription>
```



## Related topics

<dl> <dt>

[libraryDescription Element (Library Schema)](schema-librarydescription.md)
</dt> <dt>

[Search Connector Description Schema](https://msdn.microsoft.com/library/Dd940480(v=VS.85).aspx)
</dt> </dl>

 

 



