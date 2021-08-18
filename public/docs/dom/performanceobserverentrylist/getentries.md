PerformanceObserverEntryList.getEntries()
=========================================

The `getEntries()` method of the [`PerformanceObserverEntryList`](../performanceobserverentrylist) interface returns a list of explicitly *observed* [performance entry](../performanceentry) objects for a given filter. The list's members are determined by the set of [entry types](../performanceentry/entrytype) specified in the call to the [`observe()`](../performanceobserver/observe) method. The list is available in the observer's callback function (as the first parameter in the callback).

This method is exposed to [`Window`](../window) and [`Worker`](../worker) interfaces.

Syntax
------

General syntax:

    entries = list.getEntries();
    entries = list.getEntries(PerformanceEntryFilterOptions);

Specific usage:

    entries = list.getEntries({name: "entry_name", entryType: "mark"});

### Parameters

 `PerformanceEntryFilterOptions`<span class="badge inline optional">Optional</span>   
Is a `PerformanceEntryFilterOptions` dictionary, having the following fields:

-   `"name"`, the name of a performance entry.
-   `"entryType"`, the entry type. The valid entry types are listed in the [`PerformanceEntry.entryType`](../performanceentry/entrytype) method.
-   `"initiatorType"`, the type of the initiating resource (for example an HTML element). The values are defined by the [`PerformanceResourceTiming.initiatorType`](../performanceresourcetiming/initiatortype) interface.

This parameter is currently not supported on Chrome or Opera.

### Return value

A list of explicitly *observed* [`PerformanceEntry`](../performanceentry) objects that meets the criteria of the filter. The items will be in chronological order based on the entries' [`startTime`](../performanceentry/starttime). If no objects that meet the filter are found, an empty list is returned. If no argument is given, all entries are returned.

Example
-------

    function print_perf_entry(pe) {
      console.log("name: "        + pe.name      +
                  "; entryType: " + pe.entryType +
                  "; startTime: " + pe.startTime +
                  "; duration: "  + pe.duration);
    }

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

    var observe_frame = new PerformanceObserver(function(list, obs) {
      var perfEntries = list.getEntries();
      // Should only have 'frame' entries
      for (var i=0; i < perfEntries.length; i++) {
        print_perf_entry(perfEntries[i]);
      }
    });
    // subscribe to frame event only
    observe_frame.observe({entryTypes: ['frame']});

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performanceobserverentrylist-getentries">Performance Timeline Level 2<br />
<span class="small">The definition of 'getEntries()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`getEntries`

52

≤79

57

No

39

No

No

52

57

41

No

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserverEntryList/getEntries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserverEntryList/getEntries</a>
