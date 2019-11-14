---
title: Record and View TraceLogging Events
description: Record TraceLogging events with the Windows Performance Recorder (WPR) and view them with the Windows Performance Analyzer (WPA).
ms.assetid: 906589FA-F48D-4105-9E56-1EC8B86542FB
ms.topic: article
ms.date: 05/31/2018
---

# Record and View TraceLogging Events

Record TraceLogging events with the Windows Performance Recorder (WPR) and view them with the Windows Performance Analyzer (WPA).

## Prerequisites

-   Windows 10
-   The Windows 10 version of Windows Performance Recorder (WPR), and the Windows 10 version of Windows Performance Analyzer (WPA) which is art of the Windows® Assessment and Deployment Kit (Windows ADK).

> [!IMPORTANT]
> Traces captured with TraceLogging must be captured with the Windows 10 version of Windows Performance Recorder and viewed with the Windows 10 version of Windows Performance Analyzer. If you are unable to capture or decode your events, verify that you are using the Windows 10 version of the tools.

 

### 1. Capture trace data with WPR

To capture a trace on Windows Phone, see Capture TraceLogging events on Windows Phone below.

Create a Windows Performance Recorder profile (.wprp) so that you can use WPR to capture your Tracelogging events.

**Create a .WPRP file**

1.  Use the following WPRP example with the native code example in the [TraceLogging C/C++ Quick Start](tracelogging-native-quick-start.md) or the managed example in the [TraceLogging Managed Quick Start](tracelogging-managed-quick-start.md). If you are logging events from your own provider, replace the `TODO` sections with the appropriate values for your provider.

    > \[!Important\]  

     

    If you are using the TraceLogging C/C++ quick start, specify the provider GUID in the `Name` attribute of the `<EventProvider>` element. For example: `<EventProvider Id="EventProvider_SimpleTraceLoggingProvider" Name="3970F9cf-2c0c-4f11-b1cc-e3a1e9958833" />`. If you are using the managed TraceLogging quick start, specify the provider name prefaced by '\*' in the `Name` attribute of the `<EventProvider />` element. For example, `<EventProvider Name="*SimpleTraceLoggingProvider" />`.

    Sample WPRP file.

    ```XML
    <?xml version="1.0" encoding="utf-8"?>
    <!-- TODO: 
    1. Find and replace "SimpleTraceLoggingProvider" with the name of your provider.
    2. See TODO below to update GUID for your event provider
    -->
    <WindowsPerformanceRecorder Version="1.0" Author="Microsoft Corporation" Copyright="Microsoft Corporation" Company="Microsoft Corporation">
      <Profiles>
        <EventCollector Id="EventCollector_SimpleTraceLoggingProvider" Name="SimpleTraceLoggingProvider">
          <BufferSize Value="64" />
          <Buffers Value="4" />
        </EventCollector>

        <!-- TODO: 
     1. Update Name attribute in EventProvider xml element with your provider GUID, eg: Name="3970F9cf-2c0c-4f11-b1cc-e3a1e9958833". Or
        if you specify an EventSource C# provider or call TraceLoggingRegister(...) without a GUID, use star (*) before your provider
        name, eg: Name="*MyEventSourceProvider" which will enable your provider appropriately.  
     2. This sample lists one EventProvider xml element and references it in a Profile with EventProviderId xml element. 
        For your component wprp, enable the required number of providers and fix the Profile xml element appropriately
    -->
        <EventProvider Id="EventProvider_SimpleTraceLoggingProvider" Name="*SimpleTraceLoggingProvider" />
        
        <Profile Id="SimpleTraceLoggingProvider.Verbose.File" Name="SimpleTraceLoggingProvider" Description="SimpleTraceLoggingProvider" LoggingMode="File" DetailLevel="Verbose">
          <Collectors>
            <EventCollectorId Value="EventCollector_SimpleTraceLoggingProvider">
              <EventProviders>
                <!-- TODO:
     1. Fix your EventProviderId with Value same as the Id attribute on EventProvider xml element above
    -->
                <EventProviderId Value="EventProvider_SimpleTraceLoggingProvider" />
              </EventProviders>
            </EventCollectorId>
          </Collectors>
        </Profile>

        <Profile Id="SimpleTraceLoggingProvider.Light.File" Name="SimpleTraceLoggingProvider" Description="SimpleTraceLoggingProvider" Base="SimpleTraceLoggingProvider.Verbose.File" LoggingMode="File" DetailLevel="Light" />
        <Profile Id="SimpleTraceLoggingProvider.Verbose.Memory" Name="SimpleTraceLoggingProvider" Description="SimpleTraceLoggingProvider" Base="SimpleTraceLoggingProvider.Verbose.File" LoggingMode="Memory" DetailLevel="Verbose" />
        <Profile Id="SimpleTraceLoggingProvider.Light.Memory" Name="SimpleTraceLoggingProvider" Description="SimpleTraceLoggingProvider" Base="SimpleTraceLoggingProvider.Verbose.File" LoggingMode="Memory" DetailLevel="Light" />

      </Profiles>
    </WindowsPerformanceRecorder>
    
    ```

    

2.  Save the file with a .WPRP file name extension.
3.  Start the capture using WPR from an elevated (run as Administrator) Command Prompt window.

    **<path to wpr>\\wpr.exe -start GeneralProfile -start TraceLoggingProvider.wprp**

    > \[!Tip\]  
    > For general profiling purposes, you will typically also add –start GeneralProfile to the wpr.exe command line to capture system events along with the events from your provider. For simplicity the command line above omits -GeneralProfile so that only your events are gathered.

     

4.  Run the application that contains your events.
5.  Stop the trace capture.

    **<path to wpr>\\wpr.exe -stop TraceCaptureFile.etl description**

    > \[!Tip\]  
    > If you added **–start GeneralProfile** to gather system events, add **-stop GeneralProfile** to the **wpr.exe** command line above.

     

### 2. Capture TraceLogging events on Windows Phone

<span id="capturephone"></span><span id="CAPTUREPHONE"></span>

1.  Start tracelog to capture events from your provider.

    **cmdd tracelog -start test -f c:\\test.etl -guid \#providerguid**

2.  Run your test scenario to log events.
3.  Stop trace capture.

    **cmdd tracelog -stop test**

4.  Merge the system trace results with your trace results.

    **cmdd xperf -merge c:\\test.etl c:\\testmerged.etl**

5.  Retrieve the merged log file.

    **getd c:\\testmerged.etl**

### 3. View TraceLogging data using Windows Performance Analyzer.

WPA is currently the only viewer you can use to view TraceLogging trace (.etl) files.

1.  Start WPA.

    **<path to wpr>\\wpa.exe traceLoggingResults.etl**

2.  Load the trace (.etl) file that you specified in the wpa.exe command above, e.g. traceLoggingResults.etl.
3.  View your provider events. In the WPA Graph Explorer, expand **System Activity**.
4.  Double-click in the **Generic Events** pane to view the events in the **Analysis** pane.

    ![expand generic events](images/expandsystemactivity.png)

5.  In the Analysis pane, locate the events from your provider to verify that TraceLogging is working.

    In the **Provider Name** column of the **Generic Events** table, find and select the row with your provider name.

    If you have multiple providers to sort through, click the column header to sort by column name which may make it easier to find your provider.

    When you find your provider, right click on the name and select **Filter to Selection**.

    ![filter selection to provider](images/filtertoselection.png)

    The event for the SimpleTraceLoggingProvider and its value will appear in the bottom pane of the Analysis window. Expand the provider name to see the events.

    ![view the event from the simpletraceloggingprovider](images/eventview.png)

    For more information about using WPA, see [Windows Performance Analyzer](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-8.1-and-8/hh448170(v=win.10)).

## Summary and next steps

The process for recording and viewing ETW events using WPR and WPA apply equally well to TraceLogging events.

See [C/C++ Tracelogging Examples](tracelogging-c-cpp-tracelogging-examples.md) for additional TraceLogging examples.

 

 




