---
title: "Caller-Callee View - .NET Memory Sampling Data | Microsoft Docs"
description: Learn about how the Caller/Callee view displays .NET memory sampling data for a selected function and its parent and child functions in Performance Explorer.
ms.custom: SEO-VS-2020
ms.date: "11/04/2016"
ms.topic: "conceptual"
helpviewer_keywords:
  - "Caller/Callee view"
ms.assetid: 36f5b4de-5686-4f40-9e72-f4aee27d833c
author: "mikejo5000"
ms.author: "mikejo"
manager: jmartens
ms.technology: vs-ide-debug
monikerRange: 'vs-2017'
ms.workload:
  - "dotnet"
---
# Caller/Callee view - .NET memory sampling data

 [!INCLUDE [Visual Studio](~/includes/applies-to-version/vs-windows-only.md)]
The Caller/Callee view displays .NET memory profiling data for a selected function and its parent and child functions. The Caller/Callee view contains three grids.

 **Current function** is displayed in the middle grid, and it shows memory profiling information about the selected function. The values include all sampled calls to the function.

 **Functions that called the current function** is displayed in the top grid, and it shows the amount of the value of the selected (current) function that was generated by calls from the caller (parent) function.

 **Functions that were called by the current function** is displayed in the bottom grid, and it shows memory profiling data for the callee (child) functions of the selected function when the child function was called by the current function.

 Double-click a caller or callee function row to make that row the current function.

|Column|Description|
|------------|-----------------|
|**Process ID**|The process ID (PID) of the profiling run.|
|**Process Name**|The name of the process.|
|**Module Name**|The name of the module that contains the function.|
|**Module Path**|The path of the module that contains the function.|
|**Source File**|The source file that contains the definition for this function.|
|**Function Name**|The fully qualified name of the function.|
|**Function Line Number**|The line number of the start of this function in the source file.|
|**Function Address**|The address of the function.|
|**Type**|The context of the function:<br /><br /> **0** - the current function<br /><br /> **1** - a function that calls the current function<br /><br /> **2** - a function that is called by the current function<br /><br /> Only in [VSPerfReport](../profiling/vsperfreport.md) command-line reports.|
|**Level**|The depth of the function in the call tree. Only in [VSPerfReport](../profiling/vsperfreport.md) command-line reports.|
|**Inclusive Allocations**|-   For the current function, the number of objects that were allocated by the function in the profiling run. This number includes objects that were created in callee functions.<br />-   For a caller function, the number of the inclusive allocations of the current function that were generated by calls from this function.<br />-   For a callee function, the number of objects that were allocated by the instances of this function that were called by the current function. The number includes allocations that were made by functions that were called by the callee function.|
|**Inclusive Allocations %**|The percentage of all objects that were created in the profiling run that were inclusive allocations of this function.|
|**Exclusive Allocations**|-   For the current function, the number of objects that were created when the function was executing code of the function body (that is, when the function was at the top of the call stack). The number does not include objects that were created in functions that were called by the function.<br />-   For a caller function, the number of the exclusive allocations of the current function that were generated by calls from this function.<br />-   For a callee function, the number of objects that were created by the instances of this function that were called by the current function. The number does not include objects that were created by functions that were called by the callee function.|
|**Exclusive Allocations %**|The percentage of all objects that were created in the profiling run that were inclusive allocations of this function.|
|**Inclusive Bytes**|-   For the current function, the number of bytes of memory that were allocated by the function in the profiling run. The number includes memory that was allocated in functions that were called by this function.<br />-   For a caller function, the number of the inclusive bytes of the current function that were generated from calls by the caller function.<br />-   For a callee function, the number of bytes that were allocated by the instances of this function that were generated by calls from the current function. The number includes bytes that were allocated by functions that were called by the callee function.|
|**Inclusive Bytes %**|The percentage of all bytes of memory that were allocated in the profiling run that were inclusive allocations of this function.|
|**Exclusive Bytes**|-   For the current function, the number of bytes of memory that were allocated by the function in the profiling run. This number does not include memory that was allocated by functions that were called by the current function.<br />-   For a caller function, the number of the exclusive bytes of the current function that were generated by calls from the caller function.<br />-   For a callee function, the number of bytes that were allocated by instances of the function that were generated by calls from the current function. The number does not include bytes that were allocated by functions that were called by the callee function.|
|**Exclusive Bytes %**|The percentage of all bytes of memory that were allocated in the profiling run that were exclusive allocations of this function.|

## See also
- [How to: Customize report view columns](../profiling/how-to-customize-report-view-columns.md)
- [Caller/Callee view - .NET memory instrumentation data](../profiling/caller-callee-view-net-memory-instrumentation-data.md)
- [Caller/Callee view - sampling data](../profiling/caller-callee-view-sampling-data.md)
- [Caller/Callee view - instrumentation data](../profiling/caller-callee-view-instrumentation-data.md)
