---
Description: A provider is a performance DLL that provides counter data to consumers.
ms.assetid: bbb777fe-b97e-4777-b797-ec8525065610
title: Creating a Performance Extension DLL
ms.topic: article
ms.date: 05/31/2018
---

# Creating a Performance Extension DLL

A provider is a performance DLL that provides counter data to consumers. The performance DLL must export the [**OpenPerformanceData**](https://msdn.microsoft.com/en-us/library/Aa372200(v=VS.85).aspx), [**CollectPerformanceData**](https://msdn.microsoft.com/en-us/library/Aa371898(v=VS.85).aspx), and [**ClosePerformanceData**](https://msdn.microsoft.com/en-us/library/Aa371895(v=VS.85).aspx) functions. Typically, you use a module definition (.def) file to export the functions. The system calls these functions when a consumer queries performance data.

The first time a consumer calls [**RegQueryValueEx**](https://docs.microsoft.com/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa), or if the consumer uses the [**RegOpenKey**](https://docs.microsoft.com/windows/desktop/api/winreg/nf-winreg-regopenkeya) or [**RegConnectRegistry**](https://docs.microsoft.com/windows/desktop/api/winreg/nf-winreg-regconnectregistrya) function to open **HKEY\_PERFORMANCE\_DATA**, the system calls the [**OpenPerformanceData**](https://msdn.microsoft.com/en-us/library/Aa372200(v=VS.85).aspx) function for each provider that is [registered](adding-performance-counters.md) on the computer. The exception is if the provider specifies the list of objects that it supports in the \[objects\] section of the .INI file. In this case, the system calls the provider only if one of the queried objects matches an object from the list.

The [**OpenPerformanceData**](https://msdn.microsoft.com/en-us/library/Aa372200(v=VS.85).aspx) function gives each provider an opportunity to initialize its performance data structures. Then, if the **OpenPerformanceData** function returns successfully, the system calls the provider's [**CollectPerformanceData**](https://msdn.microsoft.com/en-us/library/Aa371898(v=VS.85).aspx) function. Subsequent calls to [**RegQueryValueEx**](https://docs.microsoft.com/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) cause the system to call the **CollectPerformanceData** function.

When the consumer finishes collecting performance data, it specifies **HKEY\_PERFORMANCE\_DATA** in a call to the [**RegCloseKey**](https://docs.microsoft.com/windows/desktop/api/winreg/nf-winreg-regclosekey) function. This causes the system to call the [**ClosePerformanceData**](https://msdn.microsoft.com/en-us/library/Aa371895(v=VS.85).aspx) function for each provider. The providers are then unloaded.

It is possible for multiple consumers to collect performance data at the same time. The system calls [**OpenPerformanceData**](https://msdn.microsoft.com/en-us/library/Aa372200(v=VS.85).aspx) and [**ClosePerformanceData**](https://msdn.microsoft.com/en-us/library/Aa371895(v=VS.85).aspx) functions only once for each consumer requesting performance data.

> [!Note]  
> Be sure to include extern "C" in your C++ code to prevent the compiler from adding decorations to your function names; otherwise, the system will fail to call your functions. If this occurs, the system adds a **Disable Performance Counters** value to your **Performance** key and disables your provider.

 

For more information on writing a performance DLL, see the following topics:

-   [Implementing the OpenPerformanceData function](implementing-openperformancedata.md)
-   [Implementing the CollectPerformanceData function](implementing-collectperformancedata.md)
-   [Error Handling in the DLL](error-handling-in-the-dll.md)
-   [Restricting Access to Performance Extension DLLs](restricting-access-to-performance-extension--dlls.md)
-   [Performance DLL Samples](performance-dll-samples.md)

 

 



