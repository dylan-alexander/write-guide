---
Description: The Unimodem, or Universal Modem Driver, TSP (Unimdm.tsp) provides access to nearly all standard modems.
ms.assetid: 1ea60477-f6c9-44ae-969c-515dfb0c607e
title: Unimodem TSP
ms.topic: article
ms.date: 05/31/2018
---

# Unimodem TSP

The Unimodem, or Universal Modem Driver, TSP (Unimdm.tsp) provides access to nearly all standard modems. It supports voice modems that allow half-duplex streaming. They are supported by the Wave MSP and stream control is possible. (Note that Unimodem on Windows NT 4.0 or earlier does not support voice modems, so direct stream control is not possible.)

This TSP supports an [**address type**](https://msdn.microsoft.com/en-us/library/ms733291(v=VS.85).aspx) value of LINEADDRESSTYPE\_PHONENUMBER. If the programmer wants to use the dialing rules, the TAPI 3 [**ITAddressTranslation**](https://msdn.microsoft.com/en-us/library/ms728214(v=VS.85).aspx) interface or the TAPI 2 [**lineTranslateAddress**](https://msdn.microsoft.com/en-us/library/ms736136(v=VS.85).aspx) function must be used to obtain a dialable string from a phone number in canonical format.

The Unimodem TSP is installed with Windows Server 2003 operating systems, Windows XP, Windows 2000, Windows NT, Windows Millennium Edition, Windows 98, and Windows 95.

 

 



