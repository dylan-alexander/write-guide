---
Description: A multitrack terminal can be thought of as a terminal that is a collection of other terminals. Each child terminal (a &\#0034;track&\#0034;) can be a multitrack terminal or a single-track terminal.
ms.assetid: bf23bc26-5763-45a3-a63d-e43ce2480956
title: About Multitrack Terminals
ms.topic: article
ms.date: 05/31/2018
---

# About Multitrack Terminals

A multitrack terminal can be thought of as a terminal that is a collection of other terminals. Each child terminal (a "track") can be a multitrack terminal or a single-track terminal.

All multitrack terminals expose the [**ITMultiTrackTerminal**](/windows/desktop/api/tapi3if/nn-tapi3if-itmultitrackterminal) interface, which includes generic methods for enumerating, creating, and removing track terminals from a multitrack terminal. All terminals, single-track and multitrack, expose the [**ITTerminal**](https://msdn.microsoft.com/en-us/library/ms732646(v=VS.85).aspx) interface.

A client that has a pointer to an [**ITTerminal**](https://msdn.microsoft.com/en-us/library/ms732646(v=VS.85).aspx) interface can discover whether the terminal is multitrack or single-track by querying the terminal for the [**ITMultiTrackTerminal**](/windows/desktop/api/tapi3if/nn-tapi3if-itmultitrackterminal) interface, which is exposed only on multitrack terminals.

The parent terminal may use the [**ITTerminal**](https://msdn.microsoft.com/en-us/library/ms732646(v=VS.85).aspx) interface of its track terminals, or it may require track terminals to expose private interfaces.

For more information, see [Track Terminals](track-terminals.md).

 

 



