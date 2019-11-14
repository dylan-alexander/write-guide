---
Description: The property system contains a property called System.Kind, which divides items into types according to the file name extension, and which end users can easily identify with.
ms.assetid: 1466b4c7-49ea-417a-ac94-7b45515ccb96
title: Using Kind Names
ms.topic: article
ms.date: 05/31/2018
---

# Using Kind Names

The property system contains a property called `System.Kind`, which divides items into types according to the file name extension, and which end users can easily identify with.

This topic is organized as follows:

-   [About the System.Kind Property](#about-the-systemkind-property)
-   [Kind Value Hierarchy and Registration](#kind-value-hierarchy-and-registration)
-   [Additional Resources](#additional-resources)
-   [Related topics](#related-topics)

## About the System.Kind Property

Kind was introduced in Windows Vista to express a more user-friendly notion of file type. The `System.Kind` property divides items into types and provides a Kind name that end users can identify with, such as Documents, Music, Pictures, and so forth. Hence, Kind names have come to be known as user-friendly. Because the `System.Kind` property is set to the same value for items of the same file type, and associates items that have similar characteristics with a common property, the system and the user can act on the group as a whole. For example, the `System.Kind` property can be used to limit a search to items of a specific kind, display the most relevant properties for an item in the Content view, or group similar items together.

Because Kind is a multi-value string property, you can have an `audio;video` or `link;document` Kind value. A `System.Kind` values is an ordered list of string values. In some cases, there might be only one element in that list. In other cases, an item can belong to more than one Kind. For an example of an item that belongs to more than one Kind, see the registry key example in this topic. The string values are from a predefined set of known values. The values are compared by using case-insensitive and locale-insensitive string-compare functions. These strings are not localized.

Some Kind names are already associated with properties and layout patterns. For example, items associated with `Kind.Picture` and items associated with `Kind.Document` display different properties even when they are in the same view, because of the properties and layout patterns that are already associated with those two Kind names. Each item Kind can be associated with one of four unique layout patterns that defines the number of properties displayed for each item and their layout. For more information, see [Content View based on the File Type or Kind Association](https://msdn.microsoft.com/en-us/library/Ee330739(v=VS.85).aspx).

## Kind Value Hierarchy and Registration

A `Kind` value must represent one of the values in the following list.

```
Item
   Folder
   Program
   Game
   WebHistory
   Feed
   Document
   Link
   Movie
   Music
   RecordedTV
   Video
   Picture
   Communications
      Calendar
      Contact
      E-Mail
      Task
      Journal
      Note
      InstantMessage
```

Property handlers can declare their `System.Kind` property statically through the registry, or they can provide the value dynamically through their code as they would with a standard property.

To statically define the `Kind` property, a **REG\_SZ** value entry is added under the **KindMap** registry key as shown in the following example.

```
HKEY_LOCAL_MACHINE
   Software
      Microsoft
         Windows
            CurrentVersion
               Explorer
                  KindMap
                     .recipe = Document
                     .ccc = Contact; Communications
```

Note that the `Kind` can be a single value or multiple values in a semi-colon delimited string. When providing multiple values, the most specific `Kind` value is listed first with the least specific following. In the example, Contact is named first because it is hierarchically more specific than Communications. The value **Item** is assumed and should not be explicity provided.

## Additional Resources

-   For reference documentation about properties, see [System.Kind](https://msdn.microsoft.com/library/Bb787521(v=VS.85).aspx) and [System.KindText](https://msdn.microsoft.com/library/Bb787523(v=VS.85).aspx).
-   For more information about creating new or using existing file types, see [File Types](https://msdn.microsoft.com/en-us/library/Cc144148(v=VS.85).aspx).

## Related topics

<dl> <dt>

[Understanding Property Handlers](https://msdn.microsoft.com/library/Cc144129(v=VS.85).aspx)
</dt> <dt>

[Using Property Lists](https://msdn.microsoft.com/library/Cc144133(v=VS.85).aspx)
</dt> <dt>

[Initializing Property Handlers](https://msdn.microsoft.com/library/Cc144131(v=VS.85).aspx)
</dt> <dt>

[Registering and Distributing Property Handlers](https://msdn.microsoft.com/library/Dd894084(v=VS.85).aspx)
</dt> <dt>

[Property Handler Best Practices and FAQ](https://msdn.microsoft.com/library/Dd894083(v=VS.85).aspx)
</dt> </dl>

 

 



