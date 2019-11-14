---
title: Client-side Binding
description: Binding handles are composed of a protocol sequence, the name or address of a server program host computer, and a server program endpoint. Therefore, your client program must obtain or provide this information to create a binding.
ms.assetid: 0a3bed37-95c7-4f4a-9ed3-9d57f69db523
ms.topic: article
ms.date: 05/31/2018
---

# Client-side Binding

Binding handles are composed of a protocol sequence, the name or address of a server program host computer, and a server program endpoint. Therefore, your client program must obtain or provide this information to create a binding.

If your client program uses automatic binding handles, you do not need to write special source code to create or manage the binding. The client stub calls RPC functions required to establish and maintain the binding. All you have to do is specify that your client uses automatic binding handles in the application configuration file (ACF), and design the interface accordingly. For details, see [Automatic Binding Handles](automatic-binding-handles.md).

Suppose, for example, that you were developing a client program that called remote time-stamping functions. Here, the stubs do all the work and the client only needs to include the generated header file Auto.h to obtain the function prototypes for the remote procedures. The client application calls to the remote procedures appear just as if they were calls to local procedures, as shown in the following example:


```C++
/* auto handle client application (fragment) */
#include <windows.h>
#include <stdio.h>
#include <time.h>
#include "auto.h"    // header file generated by the MIDL compiler
 
 
void main(int argc, char **argv)
{
    time_t t1;
    time_t t2;
    char * pszTime;
    ...
 
    GetTime(&t1);  // GetTime is a remote procedure
    GetTime(&t2);
 
    pszTime = ctime(&t1);
    printf("time 1= %s\n", pszTime);
 
    pszTime = ctime(&t2);
    printf("time 2= %s\n", pszTime);
 
    Shutdown();    // Shutdown is a remote procedure
    exit(0);
}
```



As you can see in the preceding example, the client application does not have to make any explicit calls to the RPC run-time library functions. The client stub manages them.

If your application uses implicit or explicit binding handles, the client must obtain the binding information and call the RPC functions to create the handles. Where the client obtains the binding information from depends on the requirements of your application. The setup program that installs your client application can store binding information in environment variables that it creates. It can also save binding information in an application-specific configuration file. Since binding information in environment variables or configuration files is usually stored as strings, your client application will need to convert the string to a binding. In Windows XP/2000 environments, binding information can be retrieved from Active Directory. For more information, see [Using String Bindings](finding-server-host-systems.md).

Most networks have a name service. Server programs can advertise themselves in the name service database. When a client begins execution, it can obtain its binding information from the name service database. For details, see [Importing from Name Service Databases](finding-server-host-systems.md).

The steps required for binding with implicit and explicit handles are discussed in the following topics:

-   [Selecting a Protocol Sequence](selecting-a-protocol-sequence.md)
-   [Finding Server Host Systems](finding-server-host-systems.md)
-   [Finding Endpoints](finding-endpoints.md)

For a brief overview of these topics, see [Connecting the Client and the Server](connecting-the-client-and-the-server.md).

 

 



