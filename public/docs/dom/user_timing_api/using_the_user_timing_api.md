Using the User Timing API
=========================

The `User Timing` interface allows the developer to create application specific [`timestamps`](../domhighrestimestamp) that are part of the browser's *performance timeline*. There are two types of *user* defined timing entry types: the "`mark`" [`entry type`](../performanceentry/entrytype) and the "`measure`" [`entry type`](../performanceentry/entrytype).

`mark` events are *named* by the application and can be set at any location in an application. `measure` events are also *named* by the application but they are placed between two marks thus they are effectively a *midpoint* between two marks.

This document shows how to create `mark` and `measure` [`performance entry types`](../performanceentry/entrytype) and how to use `User Timing` methods (which are extensions of the [`Performance`](../performance) interface) to retrieve and remove entries from the browser's *performance timeline*.

A *live* version of the examples is available on [Github](https://mdn.github.io/dom-examples/performance-apis/Using_the_User_Timing_API.html), as is the [source code](https://github.com/mdn/dom-examples/blob/master/performance-apis/Using_the_User_Timing_API.html). Pull requests, enhancement requests and [bug reports](https://github.com/mdn/dom-examples/issues) are welcome.

Performance `marks`
-------------------

A performance `mark` is a *named* [`performance entry`](../performanceentry) that is created by the application at some location in an application. The mark is a [`timestamp`](../domhighrestimestamp) in the browser's *performance timeline*.

### Creating a performance `mark`

The [`performance.mark()`](../performance/mark) method is used to create a performance mark. The method takes one argument, the *name* of the mark, as shown in the following example.

    function create_marks(ev) {
      if (performance.mark === undefined) {
        log("Create Marks: performance.mark Not supported", 0);
        return;
      } else {
      log("Create marks", 0);
      // Create several performance marks including two with the same name
      performance.mark("mark-1");
      do_work(50000);
      performance.mark("mark-2");
      do_work(50000);
      performance.mark("mark-2");
      var marks = ["mark-1", "mark-2", "mark-2"];
      for (var i=0; i < marks.length; i++)
        log("... Created mark = " + marks[i], 0);
    }

### Retrieving performance `marks`

The [`Performance`](../performance) interface has three methods to retrieve marks. The following examples shows how to use each of these methods ([`performance.getEntries()`](../performance/getentries), [`performance.getEntriesByType(entryType)`](../performance/getentriesbytype), and [`performance.getEntriesByName(name, entryType)`](../performance/getentriesbyname) ) to retrieve one or more marks.

    function display_marks(ev) {
      if (performance.getEntries === undefined) {
        log("Display Marks: performance.getEntries Not supported", 0);
        return;
      }
      log("Display marks", 0);

      // Display each mark using getEntries()
      var entries = performance.getEntries();
      var j=0;
      for (var i=0; i < entries.length; i++) {
        if (entries[i].entryType == "mark") {
          if (j == 0) { log("= getEntries()", 0); j++ }
          log("... [" + i + "] = " + entries[i].name, 0);
        }
      }

      // Display each mark using getEntriesByType()
      entries = performance.getEntriesByType("mark");
      for (var i=0; i < entries.length; i++) {
        if (i == 0) log("= getEntriesByType('mark')", 0);
        log("... [" + i + "] = " + entries[i].name, 0);
      }

      // Display each mark using getEntriesName(); must look for each mark separately
      entries = performance.getEntriesByName("mark-1","mark");
      for (var i=0; i < entries.length; i++) {
        if (i == 0) log("= getEntriesByName('mark-1', 'mark')", 0);
        log("... " + entries[i].name, 0);
      }
      entries = performance.getEntriesByName("mark-2","mark");
      for (var i=0; i < entries.length; i++) {
        if (i == 0) log("= getEntriesByName('mark-2', 'mark')", 0);
        log("... " + entries[i].name, 0);
      }
    }

### Removing performance `marks`

The [`performance.clearMarks()`](../performance/clearmarks) method is used to remove one or more marks from the browser's performance timeline. If a specific mark *name* is given to this method, only the mark(s) with that name will be removed. However, if no argument is given, then all [`performance entries`](../performanceentry) of type "`mark`" will be removed from the performance timeline. The following example demonstrates both uses of this method.

    function clear_marks(obj) {
      if (performance.clearMarks === undefined) {
        log("Clear Marks: performance.clearMarks Not supported", 0);
        return;
      }
      log("Clear marks", 0);

      if (typeof obj == "string") {
        log("... cleared '" + obj + "' mark(s)", 0);
        performance.clearMarks(obj);
      } else {
        // No argument specified so clear all marks
        log("... cleared All marks", 0);
        performance.clearMarks();
      }
    }

Performance `measures`
----------------------

A `measure` performance entry type is *named* by the application and its [`timestamp`](../domhighrestimestamp) is placed between two *named* marks thus a measure is effectively a *midpoint* between two marks in the browser's performance timeline.

### Creating a performance `measure`

A `measure` is created by calling `performance.measure(measureName, startMarkName, endMarkName)` where `measureName` is the measure's name and `startMarkName` and `endMarkName` are the start and end names, respectively, of the marks the measure will be placed between (in the performance timeline).

    function create_measures(ev) {
      if (performance.measure === undefined) {
        log("Create Measures: performance.measure Not supported", 1);
        return;
      }
      log("Create measures", 1);

      // Create several performance marks
      performance.mark("mark-A");
      do_work(50000);
      performance.mark("mark-B");

      performance.mark("mark-C");
      do_work(50000);
      performance.mark("mark-D");

      // Create some measures
      performance.measure("measure-1", "mark-A", "mark-B");
      performance.measure("measure-2", "mark-C", "mark-D");

      // Log the marks and measures
      var marks = ["mark-A", "mark-B", "mark-C", "mark-D"];
      for (var i=0; i < marks.length; i++)
        log("... Created mark = " + marks[i], 1);
      var measures = ["measures-1", "measures-2"];
      for (var i=0; i < measures.length; i++)
        log("... Created measure = " + measures[i], 1);

    }

### Retrieving performance `measures`

The [`Performance`](../performance) interface has three methods to retrieve measures. The following examples shows how to use each of these methods ([`performance.getEntries()`](../performance/getentries), [`performance.getEntriesByType(entryType)`](../performance/getentriesbytype), and [`performance.getEntriesByName(name, entryType)`](../performance/getentriesbyname)) to retrieve one or more measures.

    function display_measures(ev) {
      if (performance.getEntries === undefined) {
        log("Display Measures: performance.getEntries Not supported", 1);
        return;
      }
      log("Display measures", 1);

      // Display each measure using getEntries()
      var entries = performance.getEntries();
      var j=0;
      for (var i=0; i < entries.length; i++) {
        if (entries[i].entryType == "measure") {
          if (j == 0) { log("= getEntries()", 1); j++ }
          log("... [" + i + "] = " + entries[i].name, 1);
        }
      }

      // Display each measure using getEntriesByType
      entries = performance.getEntriesByType("measure");
      for (var i=0; i < entries.length; i++) {
        if (i == 0) log("= getEntriesByType('measure')", 1);
        log("... [" + i + "] = " + entries[i].name, 1);
      }

      // Display each measure using getEntriesName() - have to look for each measure separately
      entries = performance.getEntriesByName("measure-1","measure");
      for (var i=0; i < entries.length; i++) {
        if (i == 0) log("= getEntriesByName('measure-1', 'measure')", 1);
        log("... " + entries[i].name, 1);
      }
      entries = performance.getEntriesByName("measure-2","measure");
      for (var i=0; i < entries.length; i++) {
        if (i == 0) log("= getEntriesByName('measure-2', 'measure')", 1);
        log("... " + entries[i].name, 1);
      }
    }

### Removing performance `measures`

The [`performance.clearMeasures()`](../performance/clearmeasures) method is used to remove *measures* from the browser's performance timeline. If the method is called with a specific measure name, all measures with that name will be removed from the timeline. If the method is called with no arguments, all [`performance entries`](../performanceentry) with a type of "`measure`" will be removed from the timeline. The following examples shows both uses of this method.

    function clear_measures(obj) {
      if (performance.clearMeasures === undefined) {
        log("Clear Mearsures: performance.clearMeasures Not supported", 1);
        return;
      }
      log("Clear measures", 1);

      if (typeof obj == "string") {
        log("... cleared '" + obj + "' measure(s)", 1);
        performance.clearMeasures(obj);
      } else {
        // No argument specified so clear all measures
        log("... cleared All measures", 1);
        performance.clearMeasures();
      }
    }

Interoperability
----------------

As shown in the [`Performance`](../performance) interface's [Browser Compatibility](../performance#browser_compatibility) table, the `User Timing` methods are broadly implemented by desktop and mobile browsers (the only exceptions are no support for Desktop Safari and Mobile Safari).

See also
--------

-   [User Timing Standard](https://w3c.github.io/user-timing/); W3C Editor's Draft
-   [A Primer for Web Performance Timing APIs](https://siusin.github.io/perf-timing-primer/); Xiaoqian Wu; W3C Editor's Draft

<a href="https://developer.mozilla.org/en-US/docs/Web/API/User_Timing_API/Using_the_User_Timing_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/User_Timing_API/Using_the_User_Timing_API</a>
