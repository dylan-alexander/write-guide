---
Description: Per-user event generated by the system on attempt to launch a game. Various field values are provided by the Games Explorer system and corresponding Game Definition File (GDF) metadata provided by supported games.
ms.assetid: c870f9fb-3be1-4039-9a33-dddff17a4faa
title: WPCEVENT_GAME_START event (Wpcevent.h)
ms.topic: reference
ms.date: 05/31/2018
---

# WPCEVENT\_GAME\_START event

Per-user event generated by the system on attempt to launch a game. Various field values are provided by the Games Explorer system and corresponding Game Definition File (GDF) metadata provided by supported games.


```C++
const EVENT_DESCRIPTOR WPCEVENT_GAME_START = {0x2, 0x0, 0x10, 0x4, 0x16, 0x2, 0x8000000000000030};
```



## Parameters

<dl> <dt>

*AppID* 
</dt> <dd>

The GUID of the game that attempted to launch.

</dd> <dt>

*InstanceID* 
</dt> <dd>

The GUID used to distinguish between multiple installations.

</dd> <dt>

*AppVersion* 
</dt> <dd>

The version string for the game.

</dd> <dt>

*Path* 
</dt> <dd>

The path to the primary directory of the game installation.

</dd> <dt>

*Rating* 
</dt> <dd>

A string that identifies the rating level of a game within the rating system.

</dd> <dt>

*RatingSystem* 
</dt> <dd>

A GUID that identifies the current rating system to which the rating level applies.

</dd> <dt>

*Reason* 
</dt> <dd>

A value of the [**WPCFLAG\_ISBLOCKED**](/windows/win32/api/wpcevent/ne-wpcevent-wpcflag_isblocked) enumeration that indicates information about what events are blocked from use and what controls are in place.

</dd> <dt>

*DescCount* 
</dt> <dd>

The count of descriptors that are present in the descriptor field.

</dd> <dt>

*Descriptor* 
</dt> <dd>

A delimited string that contains descriptors that are blocked for the game.

</dd> <dt>

*PID* 
</dt> <dd>

The process ID of the game, which is used to correlate with a shim shutdown of the process.

</dd> </dl>

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                        |
| Minimum supported server<br/> | None supported<br/>                                                             |
| Header<br/>                   | <dl> <dt>Wpcevent.h</dt> </dl> |



## See also

<dl> <dt>

[Using Logging APIs for Parental Controls](using-logging-apis-for-parental-controls.md)
</dt> <dt>

[**WPC\_ARGS\_CONVERSATIONINITEVENT**](/windows/win32/api/wpcevent/ne-wpcevent-wpc_args_conversationinitevent)
</dt> </dl>

 

 



