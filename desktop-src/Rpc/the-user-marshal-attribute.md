---
title: The user_marshal Attribute
description: The \ user\_marshal\ attribute is an ACF-type attribute similar in syntax to \ represent\_as\ .
ms.assetid: 5a381b44-e271-4713-954f-a55840a92bb7
keywords:
- Remote Procedure Call RPC , attributes, user_marshal
- user_marshal
ms.topic: article
ms.date: 05/31/2018
---

# The user\_marshal Attribute

The \[ [user\_marshal](https://docs.microsoft.com/windows/desktop/Midl/user-marshal)\] attribute is an ACF-type attribute similar in syntax to \[ [represent\_as](https://docs.microsoft.com/windows/desktop/Midl/represent-as)\]. As with the IDL attribute, \[ [wire\_marshal](https://docs.microsoft.com/windows/desktop/Midl/wire-marshal)\], it offers a more efficient way to marshal data across a network. As an ACF attribute, **\[user\_marshal\]** lets you marshal custom data types that are unknown to MIDL. Each application-specific type has a corresponding transmittable type that defines the wire representation.

Your application-specific type can be a simple, composite, or pointer type. The main restriction is that the type instance must have a fixed, well-defined memory size. If the size of your type instance needs to change, use a pointer field rather than a conformant array. Alternatively, you can define a pointer to the changeable type.

As with the **\[wire\_marshal\]** attribute, you supply routines for the sizing, marshaling, unmarshaling, and freeing passes. The following table describes the four user-supplied routine names. The <type> is the userm-*type* specified in the **\[user\_marshal\]** type definition.



| Routine                                                            | Description                                                               |
|--------------------------------------------------------------------|---------------------------------------------------------------------------|
| [<type>\_UserSize](the-type-usersize-function.md)           | Sizes the RPC data buffer before marshaling on the client or server side. |
| [<type>\_UserMarshal](the-type-usermarshal-function.md)     | Marshals the data on the client or server side.                           |
| [<type>\_UserUnmarshal](the-type-userunmarshal-function.md) | Unmarshals the data on the client or server side.                         |
| [<type>\_UserFree](the-type-userfree-function.md)           | Frees the data on the server side.                                        |



 

These user-supplied routines are provided by either the client or the server application, based on the directional attributes.

If the parameter is \[ [in](https://docs.microsoft.com/windows/desktop/Midl/in)\] only, the client transmits to the server. The client needs the **<type>\_UserSize** and **<type>\_UserMarshal** functions. The server needs the **<type>\_UserUnmarshal** and **<type>\_UserFree** functions.

For an \[ [out](https://docs.microsoft.com/windows/desktop/Midl/out-idl)\]-only parameter, the server transmits to the client. The server needs the **<type>\_UserSize** and **<type>\_UserMarshal** functions, while the client needs the **<type>\_UserMarshal** function.

## Related topics

<dl> <dt>

[The wire\_marshal Attribute](the-wire-marshal-attribute.md)
</dt> <dt>

[Marshaling Rules for user marshal and wire\_marshal](marshaling-rules-for-user-marshal-and-wire-marshal.md)
</dt> <dt>

[user\_marshal](https://docs.microsoft.com/windows/desktop/Midl/user-marshal)
</dt> <dt>

[wire\_marshal](https://docs.microsoft.com/windows/desktop/Midl/wire-marshal)
</dt> <dt>

[**NdrGetUserMarshalInfo**](/windows/desktop/api/Rpcndr/nf-rpcndr-ndrgetusermarshalinfo)
</dt> </dl>

 

 




