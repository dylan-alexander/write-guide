---
Description: To determine whether a security descriptor is self-relative or absolute, call the GetSecurityDescriptorControl function and check the SE\_SELF\_RELATIVE flag of the SECURITY\_DESCRIPTOR\_CONTROL parameter.
ms.assetid: dab2844b-7df9-446c-aacf-380a0a805cbc
title: Absolute and Self-Relative Security Descriptors
ms.topic: article
ms.date: 05/31/2018
---

# Absolute and Self-Relative Security Descriptors

A [*security descriptor*](https://docs.microsoft.com/windows/desktop/SecGloss/s-gly) can be in either [*absolute*](https://docs.microsoft.com/windows/desktop/SecGloss/a-gly) or [*self-relative*](https://docs.microsoft.com/windows/desktop/SecGloss/s-gly) format. In absolute format, a security descriptor contains pointers to its information, not the information itself. In self-relative format, a security descriptor stores a [**SECURITY\_DESCRIPTOR**](/windows/desktop/api/Winnt/ns-winnt-security_descriptor) structure and associated security information in a contiguous block of memory. To determine whether a security descriptor is self-relative or absolute, call the [**GetSecurityDescriptorControl**](https://msdn.microsoft.com/en-us/library/Aa446647(v=VS.85).aspx) function and check the SE\_SELF\_RELATIVE flag of the [**SECURITY\_DESCRIPTOR\_CONTROL**](security-descriptor-control.md) parameter. You can use the [**MakeSelfRelativeSD**](https://msdn.microsoft.com/en-us/library/Aa379265(v=VS.85).aspx) and [**MakeAbsoluteSD**](https://msdn.microsoft.com/en-us/library/Aa379264(v=VS.85).aspx) functions for converting between these two formats.

The absolute format is useful when you are building a security descriptor and have pointers to all of the components, for example, when default settings for the owner, group, and discretionary ACL are available. In this case, you can call the [**InitializeSecurityDescriptor**](https://msdn.microsoft.com/en-us/library/Aa378863(v=VS.85).aspx) function to initialize a [**SECURITY\_DESCRIPTOR**](/windows/desktop/api/Winnt/ns-winnt-security_descriptor) structure, and then call functions such as [**SetSecurityDescriptorDacl**](https://msdn.microsoft.com/en-us/library/Aa379583(v=VS.85).aspx) to assign ACL and SID pointers to the security descriptor.

In self-relative format, a security descriptor always begins with a [**SECURITY\_DESCRIPTOR**](/windows/desktop/api/Winnt/ns-winnt-security_descriptor) structure, but the other components of the security descriptor can follow the structure in any order. Instead of using memory addresses, the security descriptor's components are identified by offsets from the beginning of the descriptor. This format is useful when a security descriptor must be stored on disk, transmitted by means of a communications protocol, or copied in memory.

Except for [**MakeAbsoluteSD**](https://msdn.microsoft.com/en-us/library/Aa379264(v=VS.85).aspx), all functions that return a security descriptor do so using the self-relative format. Security descriptors passed as arguments to a function can be either self-relative or absolute form. For more information, refer to the documentation for the function.

 

 



