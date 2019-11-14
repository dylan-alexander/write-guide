---
title: Offline Compiling
description: The effect-compiler tool (fxc.exe) is designed for offline compilation of HLSL shaders.
ms.assetid: 56806335-a0c7-4247-b40d-ba93486a88ac
keywords:
- fxc, offline compiling
ms.topic: article
ms.date: 05/31/2018
---

# Offline Compiling

The effect-compiler tool (fxc.exe) is designed for offline compilation of HLSL shaders.

-   [Compiling with the Current Compiler](#compiling-with-the-current-compiler)
-   [Compiling with the Legacy Compiler](#compiling-with-the-legacy-compiler)
-   [Using the Effect-Compiler tool in a Subprocess](#using-the-effect-compiler-tool-in-a-subprocess)
-   [Related topics](#related-topics)

## Compiling with the Current Compiler

The shader models supported by the current compiler are shown in [Profiles](dx-graphics-tools-fxc-syntax.md). This example compiles a pixel shader for the shader model 5.1 target.


```
fxc /T ps_5_1 /Fo PixelShader1.fxc PixelShader1.hlsl
```



In this example:

-   ps\_5\_1 is the target profile.
-   PixelShader1.fxc is the output object file containing the compiled shader.
-   PixelShader1.hlsl is the source.


```
fxc /Od /Zi /T ps_5_1 /Fo PixelShader1.fxc PixelShader1.hlsl
```



The debug options include additional options to disable compiler optimizations (Od) and enable debug information (Zi) like line numbers and symbols.

For a full listing of the command-line options, see the [Syntax](dx-graphics-tools-fxc-syntax.md) page.

## Compiling with the Legacy Compiler

Beginning with Direct3D 10, some shader models are no longer supported. These include pixel shader models: ps\_1\_1, ps\_1\_2, ps\_1\_3, and ps\_1\_4 which support very limited resources and are dependent on hardware. The compiler has been redesigned with shader model 2 (or greater) which allows for greater efficiencies with compilation. This of course will require that you are running on hardware that supports shader models 2 and greater.

Also note that you should consult the SDK release notes associated with your version of the FXC compiler for behavior affected by the /Gec switch.

## Using the Effect-Compiler tool in a Subprocess

If fxc.exe is spawned as a subprocess by an application it is important to ensure that the application checks for and reads any data in output or error pipes passed to the CreateProcess function. If the application only waits for the subprocess to finish and one of the pipes becomes full the subprocess will never finish.

The following example code illustrates waiting on a subprocess and reading the output and error pipes attached to the subprocess. The contents of the `WaitHandles` array correspond to handles for the subprocess, the pipe for stdout and the pipe for stderr.


```
  }        
```



For additional information on spawning a process see the reference page for [**CreateProcess**](https://docs.microsoft.com/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa).

## Related topics

<dl> <dt>

[Effect-Compiler Tool](fxc.md)
</dt> </dl>

 

 




