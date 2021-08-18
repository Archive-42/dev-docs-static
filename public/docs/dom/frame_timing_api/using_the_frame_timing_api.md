Using the Frame Timing API
==========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PerformanceFrameTiming` interface provides *frame* timing data about the browser's event loop. A *frame* represents the amount of work a browser does in [one event loop iteration](https://html.spec.whatwg.org/multipage/webappapis.html#processing-model-8) such as processing DOM events, resizing, scrolling, rendering, CSS animations, etc. A *frame rate* of 60 fps (frames per second) for a 60 Hz refresh rate is a common target for a good *responsive* user experience. This means the browser should process a frame in about 16.7ms.

An application can register a [`PerformanceObserver`](../performanceobserver) for "`frame`" [`performance entry types`](../performanceentry) and the observer will have data about the duration of each frame event. This data can be used to help identify areas that take too long to provide a good user experience.

This document describes how to use the [`PerformanceFrameTiming`](../performanceframetiming) interfaces including example code. For an overview of these interfaces see [Frame Timing API](../frame_timing_api).

Frame observers
---------------

<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>The *performance observer* interfaces allow an application to register an *observer* for specific [`performance event types`](../performanceentry). When one of those event types is added to the browser's *performance timeline*, the application is notified of the event via the observer's callback function that was specified when the observer was created.

Creating an observer
--------------------

To observe "`frame`" performance entry types, the application first creates a [`PerformanceObserver`](../performanceobserver) object with a specific frame observer callback. In the following example, two observers for the "`frame`" [`performance entry type`](../performanceentry/entrytype) are created and the first observer constructor uses inline function syntax.

    function create_frame_observer() {
      if (window.PerformanceObserver === undefined) return;

      // Register the performance observer
      var observe_frame = new PerformanceObserver(function(list) {
        // Log the frame entries
        var perfEntries = list.getEntriesByType("frame");
        for (var i=0; i < perfEntries.length; i++) {
          console.log("OBS #1: [" + i + "] = " + perfEntries[i].name);
        }
      });
      // Only observe 'frame' events
      observe_frame.observe({entryTypes: ['frame']});
    }

    function init () {
      create_frame_observer();

      var obs = new PerformanceObserver(frame_observer_2);
      obs.observe({entryTypes: ['frame']});
    }

    function frame_observer_2(list) {
      // Log the frame entries
      var perfEntries = list.getEntriesByType("frame");
      for (var i=0; i < perfEntries.length; i++) {
        console.log("OBS #2: [" + i + "] = " + perfEntries[i].name);
      }
    }

    <body onload="init(event)">

When the browser adds a new "`frame`" entry to the performance timeline, both of the observer callbacks will be invoked.

Registering for notifications
-----------------------------

After an observer is created, the next step is to use the [`PerformanceObserver.observe()`](../performanceobserver/observe) method to specify the set of performance events to observe. In the following example, the observer only registers for "`frame`" [`performance entry`](../performanceentry/entrytype) notifications.

     var observe_frame = new PerformanceObserver(function(list) {
       // Process the frame ...
     });
     // Only observe 'frame' events
     observe_frame.observe({entryTypes: ['frame']});

In the following example, the observer registers to be notified when several different [`performance entry types`](../performanceentry/entrytype) are added to the performance timeline.

     var observe_all = new PerformanceObserver(function(list) {
       var perfEntries = list.getEntries();
       for (var i=0; i < perfEntries.length; i++) {
         switch (perfEntries[i].entryType) {
           case "frame": process_frame(perfEntries[i]); break;
           case "mark": process_mark(perfEntries[i]); break;
           case "measure": process_measure(perfEntries[i]); break;
           case "resource": process_resource(perfEntries[i]); break;
           default: console.log("Unexpected performance entry type: " + perfEntries[i].entryType);
         }
      }
     });
     // Observe frame, mark, measure and resource events
     observe_frame.observe({entryTypes: ['frame', 'mark', 'measure', 'resource']});

Accessing frame data
--------------------

When a frame [`observer`](../performanceobserver) is invoked, the observer callback is given one argument that is a [`PerformanceObserverEntryList`](../performanceobserverentrylist) object. This object has three methods to retrieve frame data:

[`PerformanceObserverEntryList.getEntries()`](../performanceobserverentrylist/getentries)  
Returns a list of explicitly *observed* [`PerformanceEntry`](../performanceentry) objects based on the list of entry types given to [`PerformanceObserver.observe()`](../performanceobserver/observe).

[`PerformanceObserverEntryList.getEntriesByType()`](../performanceobserverentrylist/getentriesbytype)  
Returns a list of explicitly *observed* [`PerformanceEntry`](../performanceentry) objects of the given *entry type*.

[`PerformanceObserverEntryList.getEntriesByName()`](../performanceobserverentrylist/getentriesbyname)  
Returns a list of explicitly *observed* [`PerformanceEntry`](../performanceentry) objects based on the given *name* and *entry type*.

In the following example, the observer only processes "`frame`" entries.

    var THRESHOLD = 1500;
    var observe_frame = new PerformanceObserver(function(list) {
      var perfEntries = list.getEntriesByType("frame");
      for (var i=0; i < perfEntries.length; i++) {
        if (perfEntries[i].duration > THRESHOLD) {
          console.log("Warning: frame '" + THRESHOLD + "' exceeded!");
        }
      }
    });
    observe_frame.observe({entryTypes: ['frame']});

The tools will save you!
------------------------

First, perhaps using *the tools will save you* is a *bit too strong* but performance tools can certainly help identify code that is not conformant to some expected time threshold. This section briefly describes the web performance tools for the Firefox and Chrome/Canary browsers.

### Firefox performance tool

Firefox's performance tool allows the developer to *record* a piece of the user's interaction and the data obtained during the recording is used to create a *profile* of the browser's activity. The profile includes a *[waterfall](https://developer.mozilla.org/en-US/docs/Tools/Performance/Waterfall)* of the activity such as event handling, layout, painting, scripting, etc.

Firefox's performance tool also includes a *[frame rate graph](https://developer.mozilla.org/en-US/docs/Tools/Performance/Frame_rate)* which provides timestamps for each frame including the average frame rate and the minimum and maximum rates (for a specific recording session). This data, along with the waterfall data, gives an indication of where a site might be having frame related performance problems (for example, by correlating the recording's minimum rates with their respective waterfall events).

The performance tool's *[flame chart](https://developer.mozilla.org/en-US/docs/Tools/Performance/Flame_Chart)* and *[call tree](https://developer.mozilla.org/en-US/docs/Tools/Performance/Call_Tree)* tabs provide data to help analyze the site's JavaScript usage. The call tree shows where the application is spending most of its time, whereas the flame chart shows the state of the JavaScript stack for the code at every millisecond during the performance profile. This provides a way to know exactly which function was executing at any point during the recording, how long it ran, and where it was called from.

### Chrome performance tool

The Chrome (and Canary) browsers also have a performance tool with similar functions as Firefox. See [Performance profiling with the Timeline](https://developer.chrome.com/devtools/docs/timeline) for more information about this tool.

See also
--------

-   [Frame Rate (Firefox Performance Tool)](https://developer.mozilla.org/en-US/docs/Tools/Performance/Frame_rate)
-   [Frame Timing](https://w3c.github.io/frame-timing/); W3C Editor's Draft

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Frame_Timing_API/Using_the_Frame_Timing_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Frame_Timing_API/Using_the_Frame_Timing_API</a>
