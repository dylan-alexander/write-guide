---
Description: 'This application builds on the Ink Collection Sample sample by demonstrating ink strokes deletion. The sample provides the user with a menu that has four modes to choose from: ink-enabled, erasing at cusp, erasing at intersections, and erasing strokes.'
ms.assetid: cec912ee-1645-47e1-8988-626719549e55
title: Ink Erasing Sample
ms.topic: article
ms.date: 05/31/2018
---

# Ink Erasing Sample

This application builds on the [Ink Collection Sample](ink-collection-sample.md) sample by demonstrating ink strokes deletion. The sample provides the user with a menu that has four modes to choose from: ink-enabled, erasing at cusp, erasing at intersections, and erasing strokes.

In ink-enabled mode, the [InkCollector](https://msdn.microsoft.com/library/ms836493(v=MSDN.10).aspx) object collects ink as shown in [Ink Collection Sample](ink-collection-sample.md).

In an erasing mode, segments of existing ink strokes that the user touches with the cursor are erased. Also, the cusps or intersections may be marked with a red circle.

The most interesting parts of this sample lie in the `InkErase` form's `OnPaint` event handler and in the erasing functions that are called from the form's `OnMouseMove` event handler.

## Circling the Cusps and Intersections

The form's `OnPaint` event handler first paints the strokes, and depending on the application mode, may find and mark all of the cusps or intersections with a small red circle. A cusp marks the point where a stroke changes direction abruptly. An intersection marks a point where one stroke intersects with itself or another stroke.

The [Paint](https://msdn.microsoft.com/library/02745s21(v=VS.100).aspx) event occurs whenever a control is redrawn.

> [!Note]  
> The sample forces the form to redraw itself whenever a stroke is erased, or when the application mode changes, using the form's [Refresh](https://msdn.microsoft.com/library/2yzc1css(v=VS.90).aspx) method.

 


```C++
private void InkErase_OnPaint(object sender, PaintEventArgs e)
{
    Strokes strokesToPaint = myInkCollector.Ink.Strokes;

    myInkCollector.Renderer.Draw(e.Graphics, strokesToPaint);

    switch (mode)
    {
        case ApplicationMode.CuspErase:
            PaintCusps(e.Graphics, strokesToPaint);
            break;
        case ApplicationMode.IntersectErase:
            PaintIntersections(e.Graphics, strokesToPaint);
            break;
    }
}
```



In `PaintCusps`, the code iterates through each cusp in each stroke, and draws a red circle around it. The stroke's [PolylineCusps](https://msdn.microsoft.com/library/ms827853(v=MSDN.10).aspx) property returns the indices of the points within a stoke that correspond to cusps. Also, note the [Renderer](https://msdn.microsoft.com/library/ms828481(v=MSDN.10).aspx) object's [InkSpaceToPixel](https://msdn.microsoft.com/library/ms828495(v=MSDN.10).aspx) method, which converts the point to coordinates relevant to the DrawEllipse method.


```C++
private void PaintCusps(Graphics g, Strokes strokesToPaint)
{
    foreach (Stroke currentStroke in strokesToPaint)
    {
        int[] cusps = currentStroke.PolylineCusps;

        foreach (int i in cusps)
        {
            Point pt = currentStroke.GetPoint(i);

            // Convert the X, Y position to Window based pixel coordinates
            myInkCollector.Renderer.InkSpaceToPixel(g, ref pt);

            // Draw a red circle as the cusp position
            g.DrawEllipse(Pens.Red, pt.X-3, pt.Y-3, 6, 6);
        }
    }
}
```



In `PaintIntersections`, the code iterates through each stroke to find its intersections with the entire set of strokes. Note that the stroke's [FindIntersections](https://msdn.microsoft.com/library/ms827856(v=MSDN.10).aspx) method is passed a [Strokes](https://msdn.microsoft.com/library/ms827799(v=MSDN.10).aspx) collection and returns an array of floating point index values representing the intersections. The code then calculates an X-Y coordinate for each intersection, and draws a red circle around it.


```C++
private void PaintIntersections(Graphics g, Strokes strokesToPaint)
{
    foreach (Stroke currentStroke in strokesToPaint)
    {
        float[] intersections =            currentStroke.FindIntersections(strokesToPaint);
    }
}
```



## Handling a Pen That Has Two Ends

Three event handlers are defined for the [InkCollector](https://msdn.microsoft.com/library/ms836493(v=MSDN.10).aspx) object for the [CursorDown](https://msdn.microsoft.com/library/ms567611(v=VS.90).aspx), [NewPackets](https://msdn.microsoft.com/library/ms567621(v=VS.90).aspx), and [Stroke](https://msdn.microsoft.com/library/ms567622(v=VS.90).aspx) events. Each event handler checks the [Cursor](https://msdn.microsoft.com/library/ms839521(v=MSDN.10).aspx) object's [Inverted](https://msdn.microsoft.com/library/ms839525(v=MSDN.10).aspx) property to see which end of the pen is being used. When the pen is inverted:

-   The `myInkCollector_CursorDown` method makes the stroke transparent.
-   The `myInkCollector_NewPackets` method erases strokes.
-   The `myInkCollector_Stroke` method cancels the event. [NewPackets](https://msdn.microsoft.com/library/ms567621(v=VS.90).aspx) events are generated prior to the [Stroke](https://msdn.microsoft.com/library/ms567622(v=VS.90).aspx) event.

## Tracking the Cursor

Whether the user is using a pen or a mouse, [MouseMove](https://msdn.microsoft.com/library/ms567617(v=VS.90).aspx) events are generated. The MouseMove event handler first checks to determine whether the current mode is an erase mode and if any mouse button is pressed, and ignores the event if these states are not present. Then, the event handler converts the pixel coordinates for the cursor into ink space coordinates by using the [Renderer](https://msdn.microsoft.com/library/ms828481(v=MSDN.10).aspx) object's [PixelToInkSpace](https://msdn.microsoft.com/library/ms828505(v=MSDN.10).aspx) method, and calls one of the code's erase methods depending on the current erase mode.

## Erasing Strokes

The `EraseStrokes` method takes the cursor's location in ink space and generates a collection of strokes that are within `HitTestRadius` units. The `currentStroke` parameter specifies a [Stroke](https://msdn.microsoft.com/library/ms827842(v=MSDN.10).aspx) object that should not be deleted. Then the strokes collection is deleted from the collector, and the form is redrawn.


```C++
private void EraseStrokes(Point pt, Stroke currentStroke)
{
    Strokes strokesHit = myInkCollector.Ink.HitTest(pt, HitTestRadius);

    if (null!=currentStroke && strokesHit.Contains(currentStroke))
    {
        strokesHit.Remove(currentStroke);
    }

    myInkCollector.Ink.DeleteStrokes(strokesHit);

    if (strokesHit.Count > 0)
    {
        this.Refresh();
    }
}
```



## Erasing at Intersections

The `EraseAtIntersections` method iterates over each stroke that falls within the test radius and generates an array of intersections between that stroke and all the other strokes in the collection. If no intersections are found, then that entire stroke is deleted; otherwise, the nearest point on the stroke to the test point is located, and from that, the intersections on either side of the point are located, describing the segment to be removed.

The [Stroke](https://msdn.microsoft.com/library/ms827842(v=MSDN.10).aspx) object's [Split](https://msdn.microsoft.com/library/ms828477(v=MSDN.10).aspx) method is used to separate the segment from the rest of the stroke, and then the segment is deleted, leaving the rest of the stroke intact. As in `EraseStrokes`, the form is redrawn before the method returns.


```C++
private void EraseAtIntersections(Point pt)
{
    Strokes strokesHit = myInkCollector.Ink.HitTest(pt, HitTestRadius);

    foreach (Stroke currentStroke in strokesHit)
    {
        float[] intersections = currentStroke.FindIntersections(myInkCollector.Ink.Strokes);
        ...
        float findex = currentStroke.NearestPoint(pt);
        ...
        strokeToDelete = currentStroke.Split(intersections[i]);
        ...
    }
    ...
}
```



## Erasing at Cusps

For each stroke that falls within the test radius, the `EraseAtCusps` method retrieves the array of cusps from the [Stroke](https://msdn.microsoft.com/library/ms827842(v=MSDN.10).aspx) object's [PolylineCusps](https://msdn.microsoft.com/library/ms827853(v=MSDN.10).aspx) method. Each end of the stroke is also a cusp, so if the stroke only has two cusps, then the entire stroke is deleted; otherwise, the nearest point on the stroke to the test point is located, and from that, the intersections on either side of the point are located, describing the segment to be removed.

The [Stroke](https://msdn.microsoft.com/library/ms827842(v=MSDN.10).aspx) object's [Split](https://msdn.microsoft.com/library/ms828477(v=MSDN.10).aspx) method is used to separate the segment from the rest of the stroke, and then the segment is deleted, leaving the rest of the stroke intact. As in `EraseStrokes`, the form is redrawn before the method returns.


```C++
private void EraseAtCusps(Point pt)
{
    ...
    strokesHit = myInkCollector.Ink.HitTest(pt, HitTestRadius);
    
    foreach (Stroke currentStroke in strokesHit)
    {
        int[] cusps = currentStroke.PolylineCusps;
        ...
        float findex = currentStroke.NearestPoint(pt);
        ...
        strokeToDelete = currentStroke.Split(cusps[i]); 
        myInkCollector.Ink.DeleteStroke(strokeToDelete);
        ...
    }
    ...
}
```



## Closing the Form

The form's [Dispose](https://msdn.microsoft.com/library/d305e9bx(v=VS.100).aspx) method disposes the [InkCollector](https://msdn.microsoft.com/library/ms836493(v=MSDN.10).aspx) object, `myInkCollector`.

 

 



