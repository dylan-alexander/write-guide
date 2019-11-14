---
Description: 'The following illustration shows two curves: one open and one closed.'
ms.assetid: e0fb8ba1-1783-4b36-93d8-f1242425d8bd
title: Open and Closed Curves
ms.topic: article
ms.date: 05/31/2018
---

# Open and Closed Curves

The following illustration shows two curves: one open and one closed.

![illustration of an open curve (a curved line) and a closed curve (the outline of a shape)](images/aboutgdip02-art24.png)

Closed curves have an interior and therefore can be filled with a brush. The [**Graphics**](/windows/desktop/api/gdiplusgraphics/nl-gdiplusgraphics-graphics) class in Windows GDI+ provides the following methods for filling closed figures and curves: [FillRectangle](https://msdn.microsoft.com/en-us/library/ms535773(v=VS.85).aspx), [FillEllipse](https://msdn.microsoft.com/en-us/library/ms535767(v=VS.85).aspx), [FillPie](https://msdn.microsoft.com/en-us/library/ms535769(v=VS.85).aspx), [FillPolygon](https://msdn.microsoft.com/en-us/library/ms535770(v=VS.85).aspx), [FillClosedCurve](https://msdn.microsoft.com/en-us/library/ms535765(v=VS.85).aspx), [**Graphics::FillPath**](/windows/desktop/api/Gdiplusgraphics/nf-gdiplusgraphics-graphics-fillpath), and [**Graphics::FillRegion**](/windows/desktop/api/Gdiplusgraphics/nf-gdiplusgraphics-graphics-fillregion). Whenever you call one of these methods, you must pass the address of one of the specific brush types ([**SolidBrush**](/windows/desktop/api/gdiplusbrush/nl-gdiplusbrush-solidbrush), [**HatchBrush**](/windows/desktop/api/gdiplusbrush/nl-gdiplusbrush-hatchbrush), [**TextureBrush**](/windows/desktop/api/gdiplusbrush/nl-gdiplusbrush-texturebrush), [**LinearGradientBrush**](/windows/desktop/api/gdiplusbrush/nl-gdiplusbrush-lineargradientbrush), or [**PathGradientBrush**](/windows/desktop/api/gdipluspath/nl-gdipluspath-pathgradientbrush)) as an argument.

The [FillPie](https://msdn.microsoft.com/en-us/library/ms535769(v=VS.85).aspx) method is a companion to the [DrawArc](https://msdn.microsoft.com/en-us/library/ms535733(v=VS.85).aspx) method. Just as the DrawArc method draws a portion of the outline of an ellipse, the FillPie method fills a portion of the interior of an ellipse. The following example draws an arc and fills the corresponding portion of the interior of the ellipse.


```
myGraphics.FillPie(&mySolidBrush, 0, 0, 140, 70, 0, 120);
myGraphics.DrawArc(&myPen, 0, 0, 140, 70, 0, 120);
```



The following illustration shows the arc and the filled pie.

![illustration showing a segment of a filled ellipse](images/aboutgdip02-art25.png)

The [FillClosedCurve](https://msdn.microsoft.com/en-us/library/ms535765(v=VS.85).aspx) method is a companion to the [DrawClosedCurve](https://msdn.microsoft.com/en-us/library/ms535740(v=VS.85).aspx) method. Both methods automatically close the curve by connecting the ending point to the starting point. The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50). Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.


```
Point myPointArray[] =
   {Point(10, 10), Point(60, 20),Point(40, 50)};
myGraphics.DrawClosedCurve(&myPen, myPointArray, 3);
myGraphics.FillClosedCurve(&mySolidBrush, myPointArray, 3, FillModeAlternate)
```



A path can consist of several figures (subpaths). The [**Graphics::FillPath**](/windows/desktop/api/Gdiplusgraphics/nf-gdiplusgraphics-graphics-fillpath) method fills the interior of each figure. If a figure is not closed, the **Graphics::FillPath** method fills the area that would be enclosed if the figure were closed. The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie.


```
myGraphics.FillPath(&mySolidBrush, &myGraphicsPath);
myGraphics.DrawPath(&myPen, &myGraphicsPath);
```



The following illustration shows the path before and after it is filled with a solid brush. Note that the text in the string is outlined, but not filled, by the [**Graphics::DrawPath**](/windows/desktop/api/Gdiplusgraphics/nf-gdiplusgraphics-graphics-drawpath) method. It is the [**Graphics::FillPath**](/windows/desktop/api/Gdiplusgraphics/nf-gdiplusgraphics-graphics-fillpath) method that paints the interiors of the characters in the string.

![illustration that twice shows text and an open and a closed curve; these are empty the first time, and filled the second time](images/aboutgdip02-art26.png)

 

 



