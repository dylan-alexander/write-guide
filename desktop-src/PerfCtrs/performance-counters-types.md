---
Description: PDH defines the following data types.
ms.assetid: 8a2e8683-502a-4893-8b4f-5e2cf464a933
title: Performance Counters Data Types
ms.topic: article
ms.date: 05/31/2018
---

# Performance Counters Data Types

PDH defines the following data types.



| Data type         | Description                                                                                                                                                                                                                                                          |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **PDH\_HQUERY**   | Handle to a query. The [**PdhOpenQuery**](/windows/desktop/api/Pdh/nf-pdh-pdhopenquerya) function returns this handle.                                                                                                                                                                            |
| **PDH\_HCOUNTER** | Handle to a counter. The [**PdhAddCounter**](/windows/desktop/api/Pdh/nf-pdh-pdhaddcountera) function returns this handle. PDH maintains the linkage between counters and queries.                                                                                                                |
| **PDH\_HLOG**     | Handle to a log file. The [**PdhOpenLog**](/windows/desktop/api/Pdh/nf-pdh-pdhopenloga) and [**PdhBindInputDataSource**](/windows/desktop/api/Pdh/nf-pdh-pdhbindinputdatasourcea) functions return this handle.                                                                                                                |
| **PDH\_STATUS**   | PDH status value. All PDH functions return a value of type **PDH\_STATUS**. If the function succeeds, the return value is ERROR\_SUCCESS. Otherwise, the function returns a [system error code](https://docs.microsoft.com/windows/desktop/Debug/system-error-codes) or a [PDH error code](pdh-error-codes.md). |



 

 

 



