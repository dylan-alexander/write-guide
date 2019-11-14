---
Description: A process may call WSPCloseSocket on a duplicated socket and the descriptor will become deallocated. The underlying socket, however, will remain open until WSPCloseSocket is called on the last remaining descriptor.
ms.assetid: dff1e932-5e87-4ec5-995d-686d20ba6236
title: Reference Counting
ms.topic: article
ms.date: 05/31/2018
---

# Reference Counting

A process may call [**WSPCloseSocket**](https://msdn.microsoft.com/en-us/library/ms742271(v=VS.85).aspx) on a duplicated socket and the descriptor will become deallocated. The underlying socket, however, will remain open until **WSPCloseSocket** is called on the last remaining descriptor.

 

 



