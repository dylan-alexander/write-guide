---
Description: Specifies the optimal visual quality settings to use for the Windows Media Video 9 Advanced Profile encoder.
ms.assetid: 9449b5fa-4f13-4c33-bfdf-611720e8dd77
title: MFPKEY_COMPRESSIONOPTIMIZATIONTYPE Property (Wmcodecdsp.h)
ms.topic: reference
ms.date: 05/31/2018
---

# MFPKEY\_COMPRESSIONOPTIMIZATIONTYPE Property

Specifies the optimal visual quality settings to use for the Windows Media Video 9 Advanced Profile encoder.

## Constant for IPropertyBag

g\_wszWMVCCompressionOptimizationType

## Data Type

VT\_I4

## Default Value

0

## Remarks

This property provides a quick way to configure a number of video encoding options. It may be set to one of the following values.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>The codec will not force optimization and will use whatever features are specified by other properties. In many cases, the codec will use internal logic to determine settings if they are not specified. This is the default value.</td>
</tr>
<tr class="even">
<td>1</td>
<td>Enables the features that will produce the best visual quality.Using this value configures the codec as if you had set the following properties:<br/>
<ul>
<li><a href="mfpkey-bdeltaqpproperty">MFPKEY_BDELTAQP</a> = 1</li>
<li><a href="mfpkey-complexityexproperty">MFPKEY_COMPLEXITYEX</a> = 3</li>
<li><a href="mfpkey-loopfilterproperty">MFPKEY_LOOPFILTER</a> = 1</li>
<li><a href="mfpkey-motionmatchmethodproperty">MFPKEY_MOTIONMATCHMETHOD</a> = -1</li>
<li><a href="mfpkey-motionsearchlevelproperty">MFPKEY_MOTIONSEARCHLEVEL</a> = 1</li>
<li><a href="mfpkey-motionsearchrangeproperty">MFPKEY_MOTIONSEARCHRANGE</a> = -1</li>
<li><a href="mfpkey-numbframesproperty">MFPKEY_NUMBFRAMES</a> = 1</li>
</ul>
If you set any of the properties in the previous list, the value you set overrides the values associated with this setting, except for <a href="mfpkey-complexityexproperty">MFPKEY_COMPLEXITYEX</a>.<br/></td>
</tr>
</tbody>
</table>



 

Setting the value of the MFPKEY\_COMPRESSIONOPTIMIZATIONTYPE property to 1 also has the effect of setting the Dquant Option registry setting to 2, and the Motion Vector Cost Method registry setting to 1. For more information, see the web article [Using the Advanced Settings of the Windows Media Video 9 Advanced Profile Codec](https://go.microsoft.com/fwlink/p/?linkid=180526).

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                    |
| Header<br/>                   | <dl> <dt>Wmcodecdsp.h</dt> </dl> |



## See also

<dl> <dt>

[Media Foundation Properties](media-foundation-properties.md)
</dt> </dl>

 

 




