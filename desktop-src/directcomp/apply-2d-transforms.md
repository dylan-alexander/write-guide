---
title: How to apply 2D transforms
description: This topic demonstrates how to apply 2D transforms to a visual by using Microsoft DirectComposition.
ms.assetid: DED74416-C85A-4220-89BD-3F9BEF786B7D
keywords:
- how to apply DirectComposition 2D transforms
- DirectComposition 2D transforms
ms.topic: article
ms.date: 05/31/2018
---

# How to apply 2D transforms

> [!NOTE]
> For apps on Windows 10, we recommend using Windows.UI.Composition APIs instead of DirectComposition. For more info, see [Modernize your desktop app using the Visual layer](/windows/uwp/composition/visual-layer-in-desktop-apps).

This topic demonstrates how to apply 2D transforms to a visual by using Microsoft DirectComposition. The example in this topic applies a group of transforms that:

1.  Rotate the visual by 180 degrees.
2.  Scale up the visual to three times its original size.
3.  Translate (move) the visual 150 pixels to the right of its original position.

The following screen shots show the visual before and after applying the 2D transforms.

![result of applying a group of 2d transforms to a visual](images/apply2dtransform.png)

## What you need to know

### Technologies

-   [DirectComposition](directcomposition-portal.md)
-   [Direct3D 11 Graphics](https://docs.microsoft.com/windows/desktop/direct3d11/atoc-dx-graphics-direct3d-11)
-   [DirectX Graphics Infrastructure (DXGI)](https://docs.microsoft.com/windows/desktop/direct3ddxgi/dx-graphics-dxgi)

### Prerequisites

-   C/C++
-   Microsoft Win32
-   Component Object Model (COM)

## Instructions

### Step 1: Initialize DirectComposition objects

1.  Create the device object and the composition target object.
2.  Create a visual, set its content, and add it to the visual tree.

For more information, see [How to initialize DirectComposition](initialize-directcomposition.md).

### Step 2: Create the transform group array


```C++
IDCompositionTransform *pTransforms[3];
```



### Step 3: Create the transform objects, set their properties, and add them to the transform group array

1.  Use the [**IDCompositionDevice::CreateRotateTransform**](https://msdn.microsoft.com/en-us/library/Hh437400(v=VS.85).aspx), [**::CreateScaleTransform**](https://msdn.microsoft.com/en-us/library/Hh437402(v=VS.85).aspx), and [**::CreateTranslateTransform**](https://msdn.microsoft.com/en-us/library/Hh437411(v=VS.85).aspx) methods to create the transform objects.
2.  Use the member functions of the [**IDCompositionRotateTransform**](https://msdn.microsoft.com/en-us/library/Hh448924(v=VS.85).aspx), [**IDCompositionScaleTransform**](https://msdn.microsoft.com/en-us/library/Hh448990(v=VS.85).aspx), and [**IDCompositionTranslateTransform**](https://msdn.microsoft.com/en-us/library/Hh449113(v=VS.85).aspx) interfaces to set the properties of the transforms.
3.  Copy the transform interface pointers to the transform group array.


```C++
IDCompositionRotateTransform *pRotateTransform = nullptr;
IDCompositionScaleTransform *pScaleTransform = nullptr;
IDCompositionTranslateTransform *pTranslateTransform = nullptr;
IDCompositionTransform *pTransformGroup = nullptr;

// Create the rotate transform.
hr = pDevice->CreateRotateTransform(&pRotateTransform);

if (SUCCEEDED(hr))
{
    // Set the center of rotation to the center point of the visual.
    hr = pRotateTransform->SetCenterX(BITMAP_WIDTH/2.0f);
    
    if (SUCCEEDED(hr)) {
        hr = pRotateTransform->SetCenterY(BITMAP_HEIGHT/2.0f);
    }

    // Set the rotate angle to 180 degrees.
    if (SUCCEEDED(hr)) {
        hr = pRotateTransform->SetAngle(180.0f);
    }

    // Add the rotate transform to the transform group array.
    pTransforms[0] = pRotateTransform;

    // Create the scale transform.
    if (SUCCEEDED(hr)) {
        hr = pDevice->CreateScaleTransform(&pScaleTransform);
    }
}

if (SUCCEEDED(hr))
{
    // Set the scaling origin to the upper-right corner of the visual.
    hr = pScaleTransform->SetCenterX(0.0f);
    if (SUCCEEDED(hr)) {
        hr = pScaleTransform->SetCenterY(0.0f);
    }

    // Set the scaling factor to three for both the width and height. 
    if (SUCCEEDED(hr)) {
        hr = pScaleTransform->SetScaleX(3.0f);
    }
    if (SUCCEEDED(hr)) {
        hr = pScaleTransform->SetScaleY(3.0f);
    }

    // Add the scale transform to the transform group array.
    pTransforms[1] = pScaleTransform;

    // Create the translate transform.
    if (SUCCEEDED(hr)) {
        hr = pDevice->CreateTranslateTransform(&pTranslateTransform);
    }
}

if (SUCCEEDED(hr))
{
    // Move the visual 150 pixels to the right.
    hr = pTranslateTransform->SetOffsetX(150.0f);
    if (SUCCEEDED(hr)) {
        hr = pTranslateTransform->SetOffsetY(0.0f);
    }

    // Add the translate transform to the transform group array.
    pTransforms[2] = pTranslateTransform;
}
```



### Step 4: Create the transform group object

Call the [**IDCompositionDevice::CreateTransformGroup**](https://msdn.microsoft.com/en-us/library/Hh437410(v=VS.85).aspx) method to create the transform group object.


```C++
if (SUCCEEDED(hr))
{
    // Create the transform group.
    hr = pDevice->CreateTransformGroup(pTransforms, 3, &pTransformGroup);
}
```



### Step 5: Apply the transform group object to the visual

Use the [**IDCompositionVisual::SetTransform**](https://msdn.microsoft.com/en-us/library/Hh449174(v=VS.85).aspx) method to associate the Transform property of the visual with the transform group object.


```C++
if (SUCCEEDED(hr))
{
    // Apply the transform group to the visual.
    hr = pVisual->SetTransform(pTransformGroup);
}
```



### Step 6: Commit the composition

Call the [**IDCompositionDevice::Commit**](https://msdn.microsoft.com/en-us/library/Hh437393(v=VS.85).aspx) method to commit the updates to the visual to DirectComposition for processing. The result of applying the group of 2D transforms appears in the target window.


```C++
if (SUCCEEDED(hr))
{
    // Commit the composition.
    hr = pDevice->Commit();
}
```



### Step 7: Free the DirectComposition objects

Be sure to free the group of 2D transform objects when you no longer need them. The following example calls the application-defined [**SafeRelease**](https://docs.microsoft.com/windows/desktop/medfound/saferelease) macro to free the transform objects.


```C++
// Release the transform objects.
for (int i = 0; i < 3; i++)
{
    SafeRelease(&pTransforms[i]);
}
```



Also remember to free the device object, the composition target object, and the visuals before your application exits.

## Complete example


```C++
#define BITMAP_WIDTH  80.0
#define BITMAP_HEIGHT 80.0

HRESULT DemoApp::ApplyTransformGroup(IDCompositionDevice *pDevice, 
                                     IDCompositionVisual *pVisual)
{
    HRESULT hr = S_OK;

    if (pDevice == nullptr || pVisual == nullptr)
        return E_INVALIDARG; 
    
    IDCompositionTransform *pTransforms[3];

    IDCompositionRotateTransform *pRotateTransform = nullptr;
    IDCompositionScaleTransform *pScaleTransform = nullptr;
    IDCompositionTranslateTransform *pTranslateTransform = nullptr;
    IDCompositionTransform *pTransformGroup = nullptr;

    // Create the rotate transform.
    hr = pDevice->CreateRotateTransform(&pRotateTransform);

    if (SUCCEEDED(hr))
    {
        // Set the center of rotation to the center point of the visual.
        hr = pRotateTransform->SetCenterX(BITMAP_WIDTH/2.0f);
        
        if (SUCCEEDED(hr)) {
            hr = pRotateTransform->SetCenterY(BITMAP_HEIGHT/2.0f);
        }

        // Set the rotate angle to 180 degrees.
        if (SUCCEEDED(hr)) {
            hr = pRotateTransform->SetAngle(180.0f);
        }

        // Add the rotate transform to the transform group array.
        pTransforms[0] = pRotateTransform;

        // Create the scale transform.
        if (SUCCEEDED(hr)) {
            hr = pDevice->CreateScaleTransform(&pScaleTransform);
        }
    }

    if (SUCCEEDED(hr))
    {
        // Set the scaling origin to the upper-right corner of the visual.
        hr = pScaleTransform->SetCenterX(0.0f);
        if (SUCCEEDED(hr)) {
            hr = pScaleTransform->SetCenterY(0.0f);
        }

        // Set the scaling factor to three for both the width and height. 
        if (SUCCEEDED(hr)) {
            hr = pScaleTransform->SetScaleX(3.0f);
        }
        if (SUCCEEDED(hr)) {
            hr = pScaleTransform->SetScaleY(3.0f);
        }

        // Add the scale transform to the transform group array.
        pTransforms[1] = pScaleTransform;

        // Create the translate transform.
        if (SUCCEEDED(hr)) {
            hr = pDevice->CreateTranslateTransform(&pTranslateTransform);
        }
    }

    if (SUCCEEDED(hr))
    {
        // Move the visual 150 pixels to the right.
        hr = pTranslateTransform->SetOffsetX(150.0f);
        if (SUCCEEDED(hr)) {
            hr = pTranslateTransform->SetOffsetY(0.0f);
        }

        // Add the translate transform to the transform group array.
        pTransforms[2] = pTranslateTransform;
    }

    if (SUCCEEDED(hr))
    {
        // Create the transform group.
        hr = pDevice->CreateTransformGroup(pTransforms, 3, &pTransformGroup);
    }

    if (SUCCEEDED(hr))
    {
        // Apply the transform group to the visual.
        hr = pVisual->SetTransform(pTransformGroup);
    }

    if (SUCCEEDED(hr))
    {
        // Commit the composition.
        hr = pDevice->Commit();
    }

    // Release the transform objects.
    for (int i = 0; i < 3; i++)
    {
        SafeRelease(&pTransforms[i]);
    }

    // Release the transform group pointer.
    SafeRelease(&pTransformGroup);

    return hr;
}
```



## Related topics

<dl> <dt>

[Transforms](transforms.md)
</dt> </dl>

 

 




