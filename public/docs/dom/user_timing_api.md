User Timing API
===============

The `User Timing` interface allows the developer to create application specific [`timestamps`](domhighrestimestamp) that are part of the browser's *performance timeline*. There are two types of *user* defined timing event types: the "`mark`" [`event type`](performanceentry/entrytype) and the "`measure`" [`event type`](performanceentry/entrytype).

`mark` events are *named* by the application and can be set at any location in an application. `measure` events are also *named* by the application but they are placed between two marks thus they are effectively a *midpoint* between two marks.

This document provides an overview of the `mark` and `measure` [`performance event types`](performanceentry/entrytype) including the four `User Timing` methods that extend the [`Performance`](performance) interface. For more details and example code regarding these two performance event types and the methods, see [Using the User Timing API](user_timing_api/using_the_user_timing_api).

Performance `marks`
-------------------

A performance `mark` is a *named* [`performance entry`](performanceentry) that is created by the application. The mark is a [`timestamp`](domhighrestimestamp) in the browser's *performance timeline*.

### Creating a performance `mark`

The [`performance.mark()`](performance/mark) method is used to create a performance mark. The method takes one argument, the *name* of the mark (for example `performance.mark("mark-1")`).

The `mark's` [`performance entry`](performanceentry) will have the following property values:

-   [`entryType`](performanceentry/entrytype) - set to "`mark`".
-   [`name`](performanceentry/name) - set to the "`name`" given when the mark was created.
-   [`startTime`](performanceentry/starttime) - set to the [`timestamp`](domhighrestimestamp) when `mark()` was called.
-   [`duration`](performanceentry/duration) - set to "`0`" (a mark has no *duration*).

### Retrieving performance `marks`

The [`Performance`](performance) interface has three methods that can be used to retrieve a mark:

[`performance.getEntries()`](performance/getentries)  
Returns all [`performance entries`](performanceentry) in the performance timeline. Finding only `mark` entries requires checking each entry's [`entryType`](performanceentry/entrytype) for "`mark`".

[`performance.getEntriesByName(name, entryType)`](performance/getentriesbyname)  
Returns all [`performance entries`](performanceentry) in the performance timeline with the specified `name` and `entryType`, thus set `entryType` to "`mark`" to get all marks (and set `name` accordingly to retrieve more specific entries).

[`performance.getEntriesByType(entryType)`](performance/getentriesbytype)  
Returns all [`performance entries`](performanceentry) in the performance timeline with the specified `entryType`, thus set `entryType` to "`mark`" to get all marks.

### Removing performance `marks`

To remove a specific mark from the performance timeline, call `performance.clearMarks(name)` where `name` is the name of the mark(s) you want removed. If this method is called with no arguments, all mark type entries will be removed from the performance timeline.

Performance `measures`
----------------------

`measure` events are also *named* by the application but they are placed between two marks thus they are effectively a *midpoint* between two marks.

### Creating a performance `measure`

A `measure` is created by calling `performance.measure(measureName, startMarkName, endMarkName)` where `measureName` is the measure's name and `startMarkName` and `endMarkName` are the start and end names, respectively, of the marks the measure will be placed between (in the performance timeline).

The `measure's` [`performance entry`](performanceentry) will have the following property values:

-   [`entryType`](performanceentry/entrytype) - set to "`measure`".
-   [`name`](performanceentry/name) - set to the "`name`" given when the measure was created.
-   [`startTime`](performanceentry/starttime) - set to the [`timestamp`](domhighrestimestamp) when `measure()` was called.
-   [`duration`](performanceentry/duration) - set to a [`DOMHighResTimeStamp`](domhighrestimestamp) that is the duration of the measure (typically, the end mark timestamp minus the start mark timestamp).

### Retrieving performance `measures`

The [`Performance`](performance) interface has three methods that can be used to retrieve a measure:

[`performance.getEntries()`](performance/getentries)  
Returns all [`performance entries`](performanceentry) in the performance timeline. Finding the `measure` entries requires checking each entry's [`entryType`](performanceentry/entrytype) for "`measure`".

[`performance.getEntriesByName(name, entryType)`](performance/getentriesbyname)  
Returns all [`performance entries`](performanceentry) in the performance timeline with the specified `name` and `entryType`, thus set `entryType` to "`measure`" to get all measures (and set `name` accordingly to retrieve more specific entries).

[`performance.getEntriesByType(entryType)`](performance/getentriesbytype)  
Returns all [`performance entries`](performanceentry) in the performance timeline with the specified `entryType`, thus set `entryType` to "`measure`" to get all measures.

### Removing performance `measures`

To remove a specific measure from the performance timeline, call `performance.clearMeasures(name)` where `name` is the name of the measure(s) you want removed. If this method is called with no arguments, all measure type entries will be removed from the performance timeline.

Interoperability
----------------

As shown in the [`Performance`](performance) interface's [Browser Compatibility](performance#browser_compatibility) table, the `User Timing` methods are broadly implemented by desktop and mobile browsers (the only exceptions are Desktop Safari and Mobile Safari, however [the Safari Technology Preview 24 has support](https://developer.apple.com/safari/technology-preview/release-notes/#r24)).

To test your browser's support for this API, run the `perf-api-support` application.

See also
--------

-   [User Timing Standard](https://w3c.github.io/user-timing/); W3C Editor's Draft
-   [CanIUse data](https://caniuse.com/#search=user-timing)
-   [A Primer for Web Performance Timing APIs](https://siusin.github.io/perf-timing-primer/); Xiaoqian Wu; W3C Editor's Draft

<a href="https://developer.mozilla.org/en-US/docs/Web/API/User_Timing_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/User_Timing_API</a>
