---
title: Starting Up a Multicast Routing Protocol
description: The following table summarizes a series of steps in a startup interaction between a routing protocol and the multicast group manager.
ms.assetid: 14524745-5cf9-442c-a5b4-b1ef313151cf
ms.topic: article
ms.date: 05/31/2018
---

# Starting Up a Multicast Routing Protocol

The following table summarizes a series of steps in a startup interaction between a routing protocol and the multicast group manager. The first column describes actions that the routing protocol performs and the responses of the routing protocol to the multicast group manager. The second column describes the multicast group manager's responses to the routing protocol and any actions the multicast group manager performs such as callbacks. The third column presents any additional information.

Each row of the table represents one step.



| Routing protocol action                                                                                                                                                                                                                                                                                                                 | Multicast group manager action                                                                                                                                                                                                                                                                                                                                                                                                                                            | Notes                                                                                                                                                                                                                                   |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Register with the multicast group manager using the [**MgmRegisterMProtocol**](/windows/desktop/api/Mgm/nf-mgm-mgmregistermprotocol) function.                                                                                                                                                                                                                      | Return to the routing protocol a handle that the protocol must use to identify itself in subsequent MGM API calls.                                                                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                         |
| Determine if an interface is already owned, and the routing protocol that owns it using the [**MgmGetProtocolOnInterface**](/windows/desktop/api/Mgm/nf-mgm-mgmgetprotocoloninterface) function.                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | IGMP can use this function to determine the owner of an interface, and perform protocol-specific processing with the information returned by this function.                                                                             |
| Take ownership of all the interfaces on which the protocol is enabled using the [**MgmTakeInterfaceOwnership**](/windows/desktop/api/Mgm/nf-mgm-mgmtakeinterfaceownership) function.                                                                                                                                                                                | If IGMP has already taken ownership of an interface and the [**MgmTakeInterfaceOwnership**](/windows/desktop/api/Mgm/nf-mgm-mgmtakeinterfaceownership) function call is received for the same interface, contact IGMP using the [**PMGM\_DISABLE\_IGMP\_CALLBACK**](https://msdn.microsoft.com/en-us/library/Aa376678(v=VS.85).aspx) callback. Once all changes to multicast data regarding interface ownership have been made, contact IGMP again using [**PMGM\_ENABLE\_IGMP\_CALLBACK**](/windows/desktop/api/Mgm/nc-mgm-pmgm_enable_igmp_callback).<br/> | Only one protocol can own an interface at a given time, in addition to IGMP.                                                                                                                                                            |
| Determine the current state of group membership on the router. This action is performed using the group membership enumeration functions: [**MgmGroupEnumerationStart**](/windows/desktop/api/Mgm/nf-mgm-mgmgroupenumerationstart), [**MgmGroupEnumerationGetNext**](/windows/desktop/api/Mgm/nf-mgm-mgmgroupenumerationgetnext), and [**MgmGroupEnumerationEnd**](/windows/desktop/api/Mgm/nf-mgm-mgmgroupenumerationend). | Return the list of groups.                                                                                                                                                                                                                                                                                                                                                                                                                                                | Routing protocols can use the results to determine what actions to take based on the groups that have already been joined. See [Enumerating Groups](enumerating-groups.md) for a complete example of using these functions.<br/> |



 

 

 




