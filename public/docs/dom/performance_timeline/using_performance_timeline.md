Using Performance Timeline
==========================

The **[Performance Timeline](https://w3c.github.io/performance-timeline/)** standard defines extensions to the [`Performance`](../performance) interface to support client-side latency measurements within applications. The standard also includes interfaces that allow an application to be notified when specific performance events occur. Together, these interfaces can be used to help identify an application's performance bottlenecks.

Performance extensions
----------------------

**Performance Timeline** extends the [`Performance`](../performance) object with three methods that provide different mechanisms to get a set of [`performance records (metrics)`](../performanceentry), depending on the specified filter criteria. The following example show the usage of these methods [`getEntries()`](../performance/getentries), [`getEntriesByName()`](../performance/getentriesbyname) and [`getEntriesByType()`](../performance/getentriesbytype).

    function log(s) {
      var o = document.getElementsByTagName("output")[0];
      o.innerHTML += s + " <br>";
    }
    function do_work (n) {
      for (var i=0 ; i < n; i++) {
         var m = Math.random();
      }
    }
    function print_perf_entry(pe) {
      log("..name: "        + pe.name      +
          "; entryType: " + pe.entryType +
          "; startTime: " + pe.startTime +
          "; duration: "  + pe.duration);
    }
    function print_PerformanceEntries() {
      if (performance.mark === undefined) {
        log("... performance.mark Not supported");
        return;
      }

      // Create some performance entries via the mark() and measure() methods
      performance.mark("Begin");
      do_work(50000);
      performance.mark("End");
      do_work(50000);
      performance.measure("Measure1", "Begin", "End");

      // Use getEntries() to iterate all entries
      var p = performance.getEntries();
      for (var i=0; i < p.length; i++) {
        log("All Entry[" + i + "]");
        print_perf_entry(p[i]);
      }

      // Use getEntries(name, entryType) to get specific entries
      p = performance.getEntries({name : "Measure1", entryType: "measure"});
      for (var i=0; i < p.length; i++) {
        log("Begin and Measure [" + i + "]");
        print_perf_entry(p[i]);
      }

      // Use getEntriesByType() to get all "mark" entries
      p = performance.getEntriesByType("mark");
      for (var i=0; i < p.length; i++) {
        log ("Mark only [" + i + "]");
        print_perf_entry(p[i]);
      }

      // Use getEntriesByName() to get all "mark" entries named "Begin"
      p = performance.getEntriesByName("Begin", "mark");
      for (var i=0; i < p.length; i++) {
        log ("Begin and Mark [" + i + "]");
        print_perf_entry(p[i]);
      }
    }

PerformanceEntry interface
--------------------------

The `PerformanceEntry` interface encapsulates a single *performance entry* i.e. a single performance metric. This interface has four properties and a JSON *serializer* ([`toJSON()`](../performance/tojson). The following example shows the use of these properties.

    function print_PerformanceEntry(ev) {
      var properties = ["name", "entryType", "startTime", "duration"];

      // Create a few performance entries
      performance.mark("Start");
      do_work(50000);
      performance.mark("Stop");
      performance.measure("measure-1");

      var p = performance.getEntries();
      for (var i=0; i < p.length; i++) {
        log("PerfEntry[" + i + "]");
        for (var j=0; j < properties.length; j++) {
          // check each property in window.performance
          var supported = properties[j] in p[i];
          if (supported) {
            var pe = p[i];
            log("... " + properties[j] + " = " + pe[properties[j]]);
          } else {
            log("... " + properties[j] + " = Not supported");
          }
        }
      }
    }

This interface also includes a [`toJSON()`](../performanceentry/tojson) method that returns the serialization of the [`PerformanceEntry`](../performanceentry) object. The following examples show the use of this method.

    function PerfEntry_toJSON() {

      // Create a few performance entries
      performance.mark("mark-1");
      performance.mark("mark-2");
      performance.measure("meas-1", "mark-1", "mark-2");

      var peList = performance.getEntries();
      var pe = peList[0];

      if (pe.toJSON === undefined) {
        log ("PerformanceEntry.toJSON() is NOT supported");
        return;
      }

      // Print the PerformanceEntry object
      var json = pe.toJSON();
      var s = JSON.stringify(json);
      log("PerformanceEntry.toJSON = " + s);
    }

Performance Observers
---------------------

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The *performance observer* interfaces allow an application to register an *observer* for specific performance event types, and when one of those event types is recorded, the application is *notified* of the event via the observer's callback function that was specified at the time, the observer was created. When the observer (callback) is invoked the callback's parameters include a *[`performance observer entry list`](../performanceobserverentrylist)* that only contains *observed* [`performance entries`](../performanceentry). That is, the list only contains entries for the event types that were specified when the observer's [`observe()`](../performanceobserver/observe) method was invoked.

The following example shows how to register two observers: the first one registers for several event types and the second observer only registers for one event type.

    function PerformanceObservers() {
      // Create observer for all performance event types
      var observe_all = new PerformanceObserver(function(list, obs) {
        var perfEntries;

        // Print all entries
        perfEntries = list.getEntries();
        for (var i=0; i < perfEntries.length; i++) {
          print_perf_entry(perfEntries[i]);
        }

        // Print entries named "Begin" with type "mark"
        perfEntries = list.getEntriesByName("Begin", "mark");
        for (var i=0; i < perfEntries.length; i++) {
          print_perf_entry(perfEntries[i]);
        }

        // Print entries with type "mark"
        perfEntries = list.getEntriesByType("mark");
        for (var i=0; i < perfEntries.length; i++) {
          print_perf_entry(perfEntries[i]);
        }
      });
      // subscribe to all performance event types
      observe_all.observe({entryTypes: ['frame', 'mark', 'measure', 'navigation', 'resource', 'server']});

      // Create observer for just the "mark" event type
      var observe_mark = new PerformanceObserver(function(list, obs) {
        var perfEntries = list.getEntries();
        // Should only have 'mark' entries
        for (var i=0; i < perfEntries.length; i++) {
          print_perf_entry(perfEntries[i]);
        }
      });
      // subscribe to only the 'mark' event
      observe_mark.observe({entryTypes: ['mark']});
    }
    function print_perf_entry(pe) {
      log("name: "        + pe.name      +
          "; entryType: " + pe.entryType +
          "; startTime: " + pe.startTime +
          "; duration: "  + pe.duration);
    }

The [`performance observer entry list`](../performanceobserverentrylist) interface has the same three `getEntries*()` methods as the [`Performance`](../performance) interface and these methods are used to retrieve *observed* performance entries within the observer callback. These methods have been used in the above stated example.

Specifications
--------------

The interfaces described in this document are defined in the **Performance Timeline** standard which has two levels:

-   [Performance Timeline Level 2](https://w3c.github.io/performance-timeline/); Editors Draft; Work In Progress. This version introduces *performance observers* (and the [`PerformanceObserver`](../performanceobserver) and [`PerformanceObserverEntryList`](../performanceobserverentrylist) interfaces).
-   [Performance Timeline](https://www.w3.org/TR/performance-timeline/); W3C Recommendation 12 December 2013

See also
--------

-   [Performance Timeline (Overview)](../performance_timeline)
-   [A Primer for Web Performance Timing APIs](https://siusin.github.io/perf-timing-primer/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance_Timeline/Using_Performance_Timeline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance_Timeline/Using_Performance_Timeline</a>
