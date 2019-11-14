---
Description: In the original Berkeley Software Distribution (BSD) socket interface the select function was the standard (and only) means to obtain network event indications.
ms.assetid: f7f42b03-1f89-4801-abf0-396ff8b61cae
title: Selects
ms.topic: article
ms.date: 05/31/2018
---

# Selects

In the original Berkeley Software Distribution (BSD) socket interface the [**select**](/windows/desktop/api/Winsock2/nf-winsock2-select) function was the standard (and only) means to obtain network event indications. For each socket, information on read, write, or error status can be polled or waited on. See [**WSPSelect**](https://msdn.microsoft.com/en-us/library/ms742289(v=VS.85).aspx) for more information. Note that network event FD\_QOS cannot be obtained by this approach.

 

 



