---
Description: A Graphics object provides methods such as DrawLine, DrawImage, and DrawString for displaying vector images, raster images, and text.
ms.assetid: 721d0c1c-d105-4d9f-b5e9-6ca407b28c4e
title: Using Graphics Containers
ms.topic: article
ms.date: 05/31/2018
---

# Using Graphics Containers

A [**Graphics**](/windows/desktop/api/gdiplusgraphics/nl-gdiplusgraphics-graphics) object provides methods such as [DrawLine](https://msdn.microsoft.com/en-us/library/ms535748(v=VS.85).aspx), [DrawImage](https://msdn.microsoft.com/en-us/library/ms535746(v=VS.85).aspx), and [DrawString](https://msdn.microsoft.com/en-us/library/ms535759(v=VS.85).aspx) for displaying vector images, raster images, and text. A **Graphics** object also has several properties that influence the quality and orientation of the items that are drawn. For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.

A [**Graphics**](/windows/desktop/api/gdiplusgraphics/nl-gdiplusgraphics-graphics) object is often associated with a particular display device. When you use a **Graphics** object to draw in a window, the **Graphics** object is also associated with that particular window.

A [**Graphics**](/windows/desktop/api/gdiplusgraphics/nl-gdiplusgraphics-graphics) object can be thought of as a container because it holds a set of properties that influence drawing, and it is linked to device-specific information. You can create a secondary container within an existing **Graphics** object by calling the [BeginContainer](https://msdn.microsoft.com/en-us/library/ms535731(v=VS.85).aspx) method of that **Graphics** object.

The following topics cover [**Graphics**](/windows/desktop/api/gdiplusgraphics/nl-gdiplusgraphics-graphics) objects and nested containers in more detail:

-   [The State of a Graphics Object](-gdiplus-the-state-of-a-graphics-object-use.md)
-   [Nested Graphics Containers](-gdiplus-nested-graphics-containers-use.md)

 

 



