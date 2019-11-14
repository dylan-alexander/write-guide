---
Description: This sample demonstrates decoding various frames in a GIF file, reading appropriate metadata for each frame, composing frames, and rendering the animation with Direct2D.
ms.assetid: d71c66b5-d37c-4c8a-bfd7-b97c69c3b8e9
title: WIC Animated Gif Sample
ms.topic: article
ms.date: 05/31/2018
---

# WIC Animated Gif Sample

This sample demonstrates decoding various frames in a GIF file, reading appropriate metadata for each frame, composing frames, and rendering the animation with Direct2D.

This topic contains the following sections.

-   [Requirements](#requirements)
-   [Downloading the Sample](#downloading-the-sample)
-   [Building the Sample](#building-the-sample)
    -   [Using Visual Studio 2008 (preferred method)](#using-visual-studio-2008-preferred-method)
    -   [Using the Command Prompt](#using-the-command-prompt)
-   [Running the Sample](#running-the-sample)
-   [See Also](#see-also)

## Requirements

This sample has the following requirements:



|                          |                                                                                                         |
|--------------------------|---------------------------------------------------------------------------------------------------------|
| Minimum supported client | Windows 7                                                                                               |
| Windows SDK              | [Windows Software Development Kit (SDK)](https://go.microsoft.com/fwlink/p/?linkid=129787) for Windows 7 |



 

## Downloading the Sample

This sample is available in the following locations:



| Location     | Path/URL                                                                                                                  |
|--------------|---------------------------------------------------------------------------------------------------------------------------|
| Windows SDK  | \\Program Files\\Microsoft SDKs\\Windows\\v7.0\\Samples\\multimedia\\wic\\WICViewerD2D\\                                  |
| Code Gallery | [Windows Imaging Component Animated GIF Win32 Sample](https://code.msdn.microsoft.com/Windows-Imaging-Component-65abbc6a) |



 

## Building the Sample

### Using Visual Studio 2008 (preferred method)

1.  Open Windows Explorer and navigate to the directory.
2.  Double-click the icon for the .sln (solution) file to open the file in Visual Studio.
3.  In the **Build** menu, select **Build Solution**. The application will be built in the default \\Debug or \\Release directory.

### Using the Command Prompt

To build the sample by using a command prompt:

1.  Open the command prompt and navigate to the sample directory.
2.  Type `msbuild WICAnimatedGif.sln`

## Running the Sample

After the application is launched, load an image file by using the **Open** command of the **File** menu. Window resizing is supported.

## See Also

[Microsoft Windows Imaging Codec](-wic-lh.md)


[Programming Guide](-wic-programming-guide.md)


[References](-wic-codec-reference.md)


 

 



