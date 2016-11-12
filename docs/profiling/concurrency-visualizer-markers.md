---
title: "Concurrency Visualizer Markers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.markersui"
ms.assetid: c4692d17-6cd2-4ad1-8590-d7275c771c70
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Concurrency Visualizer Markers
In the Concurrency Visualizer, markers are icons that represent events in an app.  Typically, the app generates these events to designate phases or occurrences in an application.  The events can be generated by the app or by libraries and runtimes that the app uses.  
  
## Kinds of Markers  
 The Concurrency Visualizer uses three kinds of markers to represent application events: flags, messages, and spans.  
  
1.  Use a *flag* to indicate an interesting point in time in your app.  For example, you might use a flag to represent that a variable value has reached a certain threshold or that an exception was thrown.  
  
2.  A *message* also marks a point in time, but you can use it for log-style tracing.  For example, what might have been dumped to a log file you can now wrap in a message call so that you can trace it and view it in the Concurrency Visualizer. You can also use the Concurrency Visualizer to export this data to a CSV file.  
  
3.  A *span* represents an interval of time in your app, for example, one of its phases.  
  
## Marker Linkage to Threads  
 Each thread that generates markers has a separate timeline channel.  The ID of the thread that's responsible for generating the marker events is shown next to the description of the marker channel.  The ID that's shown on the left side of the marker channel matches the ID of another thread in the current process.  
  
## Marker Importance  
 Markers can have one of four importance levels: low, normal, high, and critical.  You can filter the sources of markers based on importance level.  For example, if you only want to see markers from a particular source that has normal or critical importance, you can configure the filter in the [Advanced Settings](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) dialog box.The importance of a marker is displayed in its tooltip, and in the [Markers Report](../profiling/markers-report.md).  
  
## Marker Category  
 A marker category indicates a group of marker events that come from the same source.  The Concurrency Visualizer uses color to distinguish different categories of flags and spans. You can configure the Concurrency Visualizer to use categories to filter the marker events from a particular event provider.  Use the [Advanced Settings](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) dialog box to configure the filter.  
  
## Known Sources of Markers  
 Any ETW provider can generate markers, as long as the provider adheres to certain constraints. You can configure the Concurrency Visualizer to listen to additional event sources for markers. By default, it listens to these event sources:  
  
-   [Concurrency Visualizer SDK](../profiling/concurrency-visualizer-sdk.md)  
  
-   [Task Parallel Library (TPL)](../Topic/Task%20Parallel%20Library%20\(TPL\).md)  
  
-   [Dataflow](../Topic/Dataflow%20\(Task%20Parallel%20Library\).md)  
  
-   [Parallel LINQ (PLINQ)](../Topic/Parallel%20LINQ%20\(PLINQ\).md)  
  
-   [Concurrency Runtime](/visual-cpp/parallel/concrt/concurrency-runtime)  
  
-   [Scenario Marker Support](http://msdn.microsoft.com/en-us/e3b55bc2-b451-4214-ae00-0c7f5a5baec8)  
  
-   [C++ AMP (C++ Accelerated Massive Parallelism)](/visual-cpp/parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism)  
  
 You can use the Markers tab in the [Advanced Settings](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) dialog box to control whether markers from various sources are displayed in the Concurrency Visualizer and you can filter for markers based on importance and category.  
  
## Markers from EventSource  
 The Concurrency Visualizer can also display EventSource events.  For more information, see [Visualizing EventSource Events as Markers](../profiling/visualizing-eventsource-events-as-markers.md).  
  
## See Also  
 [Flag Markers](../profiling/flag-markers.md)   
 [Message Markers](../profiling/message-markers.md)   
 [Span Markers](../profiling/span-markers.md)   
 [Visualizing EventSource Events as Markers](../profiling/visualizing-eventsource-events-as-markers.md)