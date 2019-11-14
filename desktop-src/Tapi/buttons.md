---
Description: Microsoft Telephony models a phones buttons and lamps as button-lamp pairs.
ms.assetid: 6ac912bb-8d2b-4aa3-a6e8-af86fbaabd58
title: Buttons (Telephony API)
ms.topic: article
ms.date: 05/31/2018
---

# Buttons

Microsoft Telephony models a phone's buttons and lamps as button-lamp pairs. A button with no lamp next to it, or a lamp with no button is specified using a dummy indicator for the missing lamp or button. A button with multiple lamps is modeled by using multiple button-lamp pairs.

Information associated with a phone button can be set and retrieved. When a button is pressed, the service provider sends a [**PHONE\_BUTTON**](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms725254(v=vs.85)) message to the TAPI callback function. Parameters of this message are a handle to the phone device and the button/lamp identifier of the button that was pressed. The keypad button '0' through '9', '\*', and '\#' are assigned fixed button/lamp identifiers 0 through 11.

The function [**TSPI\_phoneSetButtonInfo**](https://msdn.microsoft.com/en-us/library/ms725943(v=VS.85).aspx) sets the information associated with a button on a phone device. [**TSPI\_phoneGetButtonInfo**](https://msdn.microsoft.com/en-us/library/ms725926(v=VS.85).aspx) returns information associated with a button on a phone device. The service provider sends a PHONE\_BUTTON message to the TAPI callback function when a button on the phone is pressed.

The information associated with a button does not carry any semantic meaning as far as TSPI is concerned. It is useful for device-specific applications that interpret this information for a given phone device, or for display to the user, such as in an application's help system.

 

 



