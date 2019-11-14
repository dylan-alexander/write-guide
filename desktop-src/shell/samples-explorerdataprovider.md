---
Description: Demonstrates how to implement a Shell namespace extension, including context menu behavior and custom tasks in the browser.
title: Explorer Data Provider Sample
ms.topic: article
ms.date: 05/31/2018
ms.assetid: B1B20AF8-3DDE-467b-A49E-A77849CF9F1B
api_name: 
api_type: 
api_location: 
topic_type: 
 - kbArticle

---

# Explorer Data Provider Sample

Demonstrates how to implement a Shell namespace extension, including context menu behavior and custom tasks in the browser.

This topic contains the following sections.

-   [Requirements](#requirements)
-   [Downloading the Sample](#downloading-the-sample)
-   [Building the Sample](#building-the-sample)
-   [Running the Sample](#running-the-sample)

## Requirements



| Product                                | Minimum Product Version |
|----------------------------------------|-------------------------|
| Windows                                | Windows Vista           |
| Windows Software Development Kit (SDK) | 6.1                     |



 

## Downloading the Sample

This sample is available in the following locations.



| Location      | Path URL                                                                                               |
|---------------|--------------------------------------------------------------------------------------------------------|
| Code Gallery  | [Windows Shell Extensibility Samples on Code Gallery](https://go.microsoft.com/fwlink/p/?linkid=155658) |
| Windows 7 SDK | [Download Windows 7 SDK](https://go.microsoft.com/fwlink/p/?linkid=129787)                              |



 

In the case of the Windows SDK, once you have downloaded and installed it, you will find the samples in the installed directory. For example, use of the default installation path for the Windows 7 SDK results in the samples being placed under `C:\Program Files\Microsoft SDKs\Windows\v7.0\Samples\`.

## Building the Sample

To build the sample from the command prompt:

1.  Open the command prompt window and navigate to the **ExplorerDataProvider** project directory.
2.  Enter `msbuild ExplorerDataProvider.sln`.

To build the sample using Microsoft Visual Studio (preferred):

1.  Open Windows Explorer and navigate to the **ExplorerDataProvider** project directory.
2.  Double-click the icon for the ExplorerDataProvider.sln file to open the project in Visual Studio.
3.  From the **Build** menu, select **Build Solution**. The DLL will be built in the default \\Debug or \\Release directory.

> [!Note]  
> In the version of this sample included in the Windows SDK, the configuration for the 64-bit Release build does not include the ExplorerDataProvider.def file in the linker's **Module Definition File** option. You must specify that file yourself before building in a 64-bit environment. Add the line `ModuleDefinitionFile="ExplorerDataProvider.def"` to the VCLinkerTool section (begins at line 329) of the ExplorerDataProvider.vcproj file as shown here:
>
> <span codelanguage=""></span>
>
> <table>
> <colgroup>
> <col style="width: 100%" />
> </colgroup>
> <tbody>
> <tr class="odd">
> <td><pre><code>LinkIncremental=&quot;1&quot;
> AdditionalLibraryDirectories=&quot;&quot;c:\Program Files\Microsoft SDKs\Windows\v6.0\Lib\x64&quot;&quot;
> ModuleDefinitionFile=&quot;ExplorerDataProvider.def&quot;
> GenerateDebugInformation=&quot;true&quot;</code></pre></td>
> </tr>
> </tbody>
> </table>
>
> 
>
> The version of this sample downloadable from Code Gallery has been corrected for this issue and no extra action is required on your part.
>
>  
>
> ## Running the Sample
>
> 1.  Navigate to the directory that contains the new .dll and .propdesc file, using the command prompt or Windows Explorer.
> 2.  At the command line, type `regsvr32.exe`.
>     > [!Note]  
>     > If you run this command from an elevated command prompt, the self-registration will also register the .propdesc file automatically. If it is run from a non-elevated command prompt then the namespace extension will work, but without custom property functionality.
>
>      
>
> 3.  Open the **My Computer** folder and browse the new namespace extension present there.
>
>  
>
>  
>


