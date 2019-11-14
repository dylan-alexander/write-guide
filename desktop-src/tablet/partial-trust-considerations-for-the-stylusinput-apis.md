---
Description: Overview of partial trust issues and the StylusInput application programming interface (API).
ms.assetid: 32c26632-03f4-4f21-8c67-ebf38b67d251
title: Partial Trust Considerations for the StylusInput API
ms.topic: article
ms.date: 05/31/2018
---

# Partial Trust Considerations for the StylusInput API

The [**RealTimeStylus**](realtimestylus-class.md) that takes the *handle* parameter requires the [UIPermissionWindow.AllWindows](https://msdn.microsoft.com/library/twekyadz(v=VS.90).aspx) and [SecurityPermissionFlag.UnmanagedCode](https://msdn.microsoft.com/library/xc5yzfbx(v=VS.96).aspx) permissions, in addition to the permissions required by the constructor that takes the *attachedControl* parameter.

For more information about security and trust issues, see [Security and Trust](security-and-trust.md).

 

 



