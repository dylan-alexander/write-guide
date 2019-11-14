---
Description: Adjusts the saturation.
ms.assetid: bd71f542-36d9-4dfc-b402-35ee8e574731
title: MFPKEY_COLOR_SATURATION Property (Wmcodecdsp.h)
ms.topic: reference
ms.date: 05/31/2018
---

# MFPKEY\_COLOR\_SATURATION Property

Adjusts the saturation.

## Constant for IPropertyBag

Available only by using [**IPropertyStore**](https://msdn.microsoft.com/en-us/library/Bb761474(v=VS.85).aspx).

## Data Type

VT\_I4

## Default Value

0

## Applies To

-   [Color Control Transform DSP](colorcontroltransform.md)

## Remarks

Saturation adjustment is performed by multiplying the Cb and Cr values by a constant.

This property has a range of -127 to 127. Zero indicates no change in saturation.

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

 

 




