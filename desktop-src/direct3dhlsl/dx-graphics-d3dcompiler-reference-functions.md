---
title: Functions
description: This section contains information about the following Direct3D HLSL compiler functions
ms.assetid: aacc5207-3ec8-4031-b5c9-f7c0fb7b7095
keywords:
- functions, Compiler
ms.topic: article
ms.date: 05/31/2018
topic_type: 
- kbArticle
api_name: 
api_type: 
api_location: 
---

# Functions

This section contains information about the following Direct3D HLSL compiler functions:

## In this section



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Topic</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="d3d11reflect"><strong>D3D11Reflect</strong></a><br/></td>
<td>Gets a pointer to a reflection interface.<br/></td>
</tr>
<tr class="even">
<td><a href="d3dcompile"><strong>D3DCompile</strong></a><br/></td>
<td>Compile HLSL code or an effect file into bytecode for a given target.<br/></td>
</tr>
<tr class="odd">
<td><a href="d3dcompile2"><strong>D3DCompile2</strong></a><br/></td>
<td>Compiles Microsoft High Level Shader Language (HLSL) code into bytecode for a given target.<br/></td>
</tr>
<tr class="even">
<td><a href="d3dcompilefromfile"><strong>D3DCompileFromFile</strong></a><br/></td>
<td><blockquote>
[!Note]<br />
You can use this API to develop your Windows Store apps, but you can't use it in apps that you submit to the Windows Store. Refer to the section, &quot;Compiling shaders for UWP&quot;, in the remarks for <a href="d3dcompile2"><strong>D3DCompile2</strong></a>.
</blockquote>
<br/> Compiles HLSL code into bytecode for a given target.<br/></td>
</tr>
<tr class="odd">
<td><a href="d3dcompressshaders"><strong>D3DCompressShaders</strong></a><br/></td>
<td><blockquote>
[!Note]<br />
You can use this API to develop your Windows Store apps, but you can't use it in apps that you submit to the Windows Store.
</blockquote>
<br/> Compresses a set of shaders into a more compact form. <br/></td>
</tr>
<tr class="even">
<td><a href="d3dcreateblob"><strong>D3DCreateBlob</strong></a><br/></td>
<td>Creates a buffer.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/D3Dcompiler/nf-d3dcompiler-d3dcreatefunctionlinkinggraph"><strong>D3DCreateFunctionLinkingGraph</strong></a><br/></td>
<td>Creates a function-linking-graph interface. <br/>
<blockquote>
[!Note]<br />
This function is part of the HLSL shader linking technology that you can use on all Direct3D 11 platforms to create precompiled HLSL functions, package them into libraries, and link them into full shaders at run time.
</blockquote>
<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/D3Dcompiler/nf-d3dcompiler-d3dcreatelinker"><strong>D3DCreateLinker</strong></a><br/></td>
<td>Creates a linker interface. <br/>
<blockquote>
[!Note]<br />
This function is part of the HLSL shader linking technology that you can use on all Direct3D 11 platforms to create precompiled HLSL functions, package them into libraries, and link them into full shaders at run time.
</blockquote>
<br/></td>
</tr>
<tr class="odd">
<td><a href="d3ddecompressshaders"><strong>D3DDecompressShaders</strong></a><br/></td>
<td><blockquote>
[!Note]<br />
You can use this API to develop your Windows Store apps, but you can't use it in apps that you submit to the Windows Store.
</blockquote>
<br/> Decompresses one or more shaders from a compressed set. <br/></td>
</tr>
<tr class="even">
<td><a href="d3ddisassemble"><strong>D3DDisassemble</strong></a><br/></td>
<td>Disassembles compiled HLSL code.<br/></td>
</tr>
<tr class="odd">
<td><a href="d3ddisassemble10effect"><strong>D3DDisassemble10Effect</strong></a><br/></td>
<td>Disassembles compiled HLSL code from a Direct3D10 effect.<br/></td>
</tr>
<tr class="even">
<td><a href="d3ddisassemble11trace"><strong>D3DDisassemble11Trace</strong></a><br/></td>
<td>Disassembles a section of compiled HLSL code that is specified by shader trace steps.<br/></td>
</tr>
<tr class="odd">
<td><a href="d3ddisassembleregion"><strong>D3DDisassembleRegion</strong></a><br/></td>
<td>Disassembles a specific region of compiled HLSL code.<br/></td>
</tr>
<tr class="even">
<td><a href="d3dgetblobpart"><strong>D3DGetBlobPart</strong></a><br/></td>
<td>Retrieves a specific part from a compilation result.<br/></td>
</tr>
<tr class="odd">
<td><a href="d3dgetdebuginfo"><strong>D3DGetDebugInfo</strong></a><br/></td>
<td><blockquote>
[!Note]<br />
You can use this API to develop your Windows Store apps, but you can't use it in apps that you submit to the Windows Store.
</blockquote>
<br/> Gets shader debug information.<br/></td>
</tr>
<tr class="even">
<td><a href="d3dgetinputandoutputsignatureblob"><strong>D3DGetInputAndOutputSignatureBlob</strong></a><br/></td>
<td><blockquote>
[!Note]<br />
<a href="d3dgetinputandoutputsignatureblob"><strong>D3DGetInputAndOutputSignatureBlob</strong></a> may be altered or unavailable for releases after Windows 8.1. Instead use <a href="d3dgetblobpart"><strong>D3DGetBlobPart</strong></a> with the <a href="d3d-blob-part"><strong>D3D_BLOB_INPUT_AND_OUTPUT_SIGNATURE_BLOB</strong></a> value.
</blockquote>
<br/> Gets the input and output signatures from a compilation result.<br/></td>
</tr>
<tr class="odd">
<td>[<strong>D3DGetInputSignatureBlob</strong>](d3dgetinputsignatureblob.md)<br/></td>
<td><blockquote>
[!Note]<br />
<a href="d3dgetinputsignatureblob"><strong>D3DGetInputSignatureBlob</strong></a> may be altered or unavailable for releases after Windows 8.1. Instead use <a href="d3dgetblobpart"><strong>D3DGetBlobPart</strong></a> with the <a href="d3d-blob-part"><strong>D3D_BLOB_INPUT_SIGNATURE_BLOB</strong></a> value.
</blockquote>
<br/> Gets the input signature from a compilation result.<br/></td>
</tr>
<tr class="even">
<td><a href="d3dgetoutputsignatureblob"><strong>D3DGetOutputSignatureBlob</strong></a><br/></td>
<td><blockquote>
[!Note]<br />
<a href="d3dgetoutputsignatureblob"><strong>D3DGetOutputSignatureBlob</strong></a> may be altered or unavailable for releases after Windows 8.1. Instead use <a href="d3dgetblobpart"><strong>D3DGetBlobPart</strong></a> with the <a href="d3d-blob-part"><strong>D3D_BLOB_OUTPUT_SIGNATURE_BLOB</strong></a> value.
</blockquote>
<br/> Gets the output signature from a compilation result.<br/></td>
</tr>
<tr class="odd">
<td><a href="d3dgettraceinstructionoffsets"><strong>D3DGetTraceInstructionOffsets</strong></a><br/></td>
<td>Retrieves the byte offsets for instructions within a section of shader code.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/D3Dcompiler/nf-d3dcompiler-d3dloadmodule"><strong>D3DLoadModule</strong></a><br/></td>
<td>Creates a shader module interface from source data for the shader module. <br/>
<blockquote>
[!Note]<br />
This function is part of the HLSL shader linking technology that you can use on all Direct3D 11 platforms to create precompiled HLSL functions, package them into libraries, and link them into full shaders at run time.
</blockquote>
<br/></td>
</tr>
<tr class="odd">
<td><a href="d3dpreprocess"><strong>D3DPreprocess</strong></a><br/></td>
<td>Preprocesses uncompiled HLSL code.<br/></td>
</tr>
<tr class="even">
<td><a href="d3dreadfiletoblob"><strong>D3DReadFileToBlob</strong></a><br/></td>
<td><blockquote>
[!Note]<br />
You can use this API to develop your Windows Store apps, but you can't use it in apps that you submit to the Windows Store.
</blockquote>
<br/> Reads a file that is on disk into memory.<br/></td>
</tr>
<tr class="odd">
<td><a href="d3dreflect"><strong>D3DReflect</strong></a><br/></td>
<td>Gets a pointer to a reflection interface.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/D3Dcompiler/nf-d3dcompiler-d3dreflectlibrary"><strong>D3DReflectLibrary</strong></a><br/></td>
<td>Creates a library-reflection interface from source data that contains an HLSL library of functions. <br/>
<blockquote>
[!Note]<br />
This function is part of the HLSL shader linking technology that you can use on all Direct3D 11 platforms to create precompiled HLSL functions, package them into libraries, and link them into full shaders at run time.
</blockquote>
<br/></td>
</tr>
<tr class="odd">
<td><a href="d3dsetblobpart"><strong>D3DSetBlobPart</strong></a><br/></td>
<td>Sets information in a compilation result.<br/></td>
</tr>
<tr class="even">
<td><a href="d3dstripshader"><strong>D3DStripShader</strong></a><br/></td>
<td>Removes unwanted blobs from a compilation result.<br/></td>
</tr>
<tr class="odd">
<td><a href="d3dwriteblobtofile"><strong>D3DWriteBlobToFile</strong></a><br/></td>
<td><blockquote>
[!Note]<br />
You can use this API to develop your Windows Store apps, but you can't use it in apps that you submit to the Windows Store.
</blockquote>
<br/> Writes a memory blob to a file on disk.<br/></td>
</tr>
</tbody>
</table>



 

## Related topics

<dl> <dt>

[D3DCompiler Reference](dx-graphics-d3dcompiler-reference.md)
</dt> </dl>

 

 





