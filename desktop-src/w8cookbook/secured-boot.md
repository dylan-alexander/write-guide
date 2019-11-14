---
title: Early launch antimalware
description: Early launch antimalware
ms.assetid: 4064CD44-FC50-48DE-8490-F592ED21CB7E
ms.topic: article
ms.date: 05/31/2018
---

# Early launch antimalware

## Platforms

<dl> **Clients** - Windows 8  
**Servers** - Windows Server 2012  
</dl>

## Description

As antimalware (AM) software has become better and better at detecting runtime malware, attackers are also becoming better at creating rootkits that can hide from detection. Detecting malware that starts early in the boot cycle is a challenge that most AM vendors address diligently. Typically, they create system hacks that are not supported by the host operating system and can actually result in placing the computer in an unstable state. Up to this point, Windows has not provided a good way for AM to detect and resolve these early boot threats.

Windows 8 introduces a new feature called Secure Boot, which protects the Windows boot configuration and components, and loads an Early Launch Anti-malware (ELAM) driver. This driver starts before other boot-start drivers and enables the evaluation of those drivers and helps the Windows kernel decide whether they should be initialized.

## Manifestation

By being launched first by the kernel, ELAM is ensured to be launched before any third-party software, and is therefore able to detect malware in the boot process and prevent it from initializing.

## Mitigation

Boot drivers are initialized based on the classification that is returned from the ELAM driver according to an initialization policy. By default, the policy initializes known good and unknown drivers, but will not initialize known bad drivers. A system administrator can specify a custom policy through Group Policy that can prevent unknown drivers from initializing or can enable drivers that are critical to the boot process, but have been tampered with, boot to be initialized.

## Solution

An ELAM driver must register for kernel callbacks to get info about each boot-start driver as it is initializing. The ELAM driver can then return a classification for each driver. These functions are required:

<dl> IoRegisterBootDriverCallback()  
IoUnRegisterBootDriverCallback()  
</dl> An ELAM driver can also register for registry callbacks. Doing so enables the ELAM driver to inspect the configuration data that is used by each boot-start driver. The ELAM driver can then block or modify the data before it is used by the boot-start drivers, if necessary. These functions are required:

<dl> CmRegisterCallbackEx()  
CmUnRegisterCallback()  
</dl> A more detailed description of ELAM driver requirements and API usage is documented in a white paper on MSDN called Early Launch Antimalware.

## Tests

ELAM drivers must be specially signed by Microsoft to ensure they are started by the Windows kernel early in the boot process. To get the signature, ELAM drivers must pass a set of certification tests to verify performance and other behavior. These tests are included in the Windows Hardware Certification Kit.

## Resources

-   [Early Launch Antimalware Whitepaper](https://go.microsoft.com/fwlink/p/?LinkId=325481)
-   [CmRegisterCallbackEx()](https://go.microsoft.com/fwlink/p/?LinkId=325482)
-   [CmUnRegisterCallback()](https://go.microsoft.com/fwlink/p/?LinkId=325483)
-   [IoRegisterBootDriverCallback()](https://go.microsoft.com/fwlink/p/?LinkId=325484)
-   [IoUnRegisterBootDriverCallback()](https://go.microsoft.com/fwlink/p/?LinkId=325485)
-   [Certifying hardware with the Windows Hardware Certification Kit Build Conference presentation](https://go.microsoft.com/fwlink/p/?LinkId=325486)
-   [Download Kits and Tools](https://go.microsoft.com/fwlink/p/?LinkId=325487)

 

 




