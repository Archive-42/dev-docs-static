Performance Timeline
====================

The **Performance Timeline** API defines extensions to the [`Performance`](performance) interface to support client-side latency measurements within applications. The extensions provide interfaces to retrieve [performance entry metrics](performanceentry) based on specific filter criteria. The standard also includes interfaces that allow an application to define *[performance observer](#performance_observers)* callbacks that are notified when specific performance events are added to the browser's *performance timeline*.

This document provides an overview of the standard's interfaces. For more details about the interfaces, see the reference pages and [Using Performance Timeline](performance_timeline/using_performance_timeline).

**Note:** This feature is available in [Web Workers](web_workers_api).

Performance extensions
----------------------

The Performance Timeline API extends the [`Performance`](performance) interface with three methods that provide different mechanisms to get a set of [`performance records (metrics)`](performanceentry), depending on the specified filter criteria. The methods are:

[`getEntries()`](performance/getentries)  
Returns all recorded [`performance entries`](performanceentry) or, optionally, the entries based on the specified [`name`](performanceentry/name), [`performance type`](performanceentry/entrytype) and/or the [`initiatorType`](performanceresourcetiming/initiatortype) (such as an HTML element).

[`getEntriesByName()`](performance/getentriesbyname)  
Returns the recorded [`performance entries`](performanceentry) based on the specified [`name`](performanceentry/name) and optionally the [`performance type`](performanceentry/entrytype).

[`getEntriesByType()`](performance/getentriesbytype)  
Returns the recorded [`performance entries`](performanceentry) based on the specified [`performance type`](performanceentry/entrytype).

PerformanceEntry interface
--------------------------

The [`PerformanceEntry`](performanceentry) interface encapsulates a single *performance entry* — that is, a single data point or metric in the *performance timeline*. This interface has the following four properties, and these properties are extended (with additional constraints) by other interfaces (such as [`PerformanceMark`](performancemark)):

[`name`](performanceentry/name)  
The name of the performance entry when the metric was created.

[`entryType`](performanceentry/entrytype)  
The type of performance metric (for example, "`mark`").

[`startTime`](performanceentry/starttime)  
A [`high resolution timestamp`](domhighrestimestamp) representing the starting time for the performance entry.

[`duration`](performanceentry/duration)  
A [high resolution timestamp](domhighrestimestamp) representing the time value of the duration of the performance event. (Some performance [entry types](performanceentry/entrytype) have no concept of *duration* and this value is set to `'0'` for such types.)

This interface includes a [`toJSON()`](performanceentry/tojson) method that returns the serialization of the [`PerformanceEntry`](performanceentry) object. The serialization is specific to the performance entry's [`type`](performanceentry/entrytype).

Performance observers
---------------------

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The *performance observer* interfaces allow an application to register an *observer* for specific performance event types, and when one of those event types is recorded, the application is *notified* of the event via the observer's callback function that was specified when the observer was created.

When the observer (callback) is invoked, the callback's parameters include a *[`performance observer entry list`](performanceobserverentrylist)* that contains only *observed* [`performance entries`](performanceentry). That is, the list contains entries only for the event types that were specified when the observer's [`observe()`](performanceobserver/observe) method was invoked. The [`performance observer entry list`](performanceobserverentrylist) interface has the same three `getEntries*()` methods as the [`Performance`](performance) interface. However, note there is one key difference with these methods; the [`performance observer entry list`](performanceobserverentrylist) versions are used to retrieve *observed* performance entries within the observer callback.

Besides the [`PerformanceObserver's`](performanceobserver) interface's [`observe()`](performanceobserver/observe) method (which is used to register the [`entry types`](performanceentry/entrytype) to *observe*), the [`PerformanceObserver`](performanceobserver) interface also has a [`disconnect()`](performanceobserver/disconnect) method that stops an observer from receiving further events.

Performance observers were added to the `Level 2` version of the standard and were not widely implemented.

Implementation status
---------------------

A summary of the interfaces' implementation status is provided below, including a link to more detailed information.

-   Performance interface extensions: As shown in the [`Performance`](performance) interface's [Browser Compatibility](performance#browser_compatibility) table, most of these interfaces are broadly implemented by desktop browsers and have less support on mobile devices.
-   PerformanceEntry: As shown in the [`PerformanceEntry`](performanceentry) interface's [Browser Compatibility](performanceentry#browser_compatibility) table, most of these interfaces are broadly implemented by desktop browsers and have less support on mobile devices.
-   Performance Observers <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>: As shown in the [`PerformanceObserver`](performanceobserver) interface's [Browser Compatibility](performanceobserver#browser_compatibility) table, this interface has no shipping implementations.

To test your browser's support for these interfaces, run the `perf-api-support` application.

See also
--------

-   [A Primer for Web Performance Timing APIs](https://siusin.github.io/perf-timing-primer/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance_Timeline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance_Timeline</a>
