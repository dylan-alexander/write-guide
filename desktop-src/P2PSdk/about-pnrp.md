---
Description: The Peer Name Resolution Protocol (PNRP) Namespace Provider (NSP) is a serverless name resolution technology that allows nodes to discover each other.
ms.assetid: e11d0f07-f3a0-4c0f-94ce-1d4944a34230
title: About PNRP
ms.topic: article
ms.date: 05/31/2018
---

# About PNRP

The Peer Name Resolution Protocol (PNRP) Namespace Provider (NSP) is a serverless name resolution technology that allows nodes to discover each other. PNRP uses the Winsock 2 Namespace Provider API.

IPv6 support is required by PNRP and is the only Internet Protocol native to the API. However, PNRP can resolve IPv4 addresses via the 6to4 or [Teredo](https://docs.microsoft.com/windows/desktop/Teredo/portal) transition technologies. Windows XP with Service Pack 1 (SP1) users must download the [Advanced Networking Pack](https://go.microsoft.com/fwlink/p/?linkid=93617) to enable the IPv6 support required by PNRP.

> [!Note]  
> Applications using PNRP in an environment with a firewall require exception groups that cover the port specific to the application, as well as port '3540-UDP' for PNRP. These exception groups should be enabled whenever the application is running.

 

While PNRP 2.0 is native to the Windows Vista and Windows Server 2008 platforms, Windows XP users must download Windows Update [KB920342](https://go.microsoft.com/fwlink/p/?linkid=93616) to upgrade to PNRP 2.0.

 

 



