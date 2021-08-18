PerformanceObserverEntryList
============================

The `PerformanceObserverEntryList` interface is a list of [peformance events](performanceentry) that were explicitly *observed* via the [`observe()`](performanceobserver/observe) method.

Note: this interface is exposed to [`Window`](window) and [`Worker`](worker).

Methods
-------

[`PerformanceObserverEntryList.getEntries()`](performanceobserverentrylist/getentries)  
Returns a list of explicitly *observed* [`PerformanceEntry`](performanceentry) objects based on the given *filter*.

[`PerformanceObserverEntryList.getEntriesByType()`](performanceobserverentrylist/getentriesbytype)  
Returns a list of explicitly *observed* [`PerformanceEntry`](performanceentry) objects of the given *entry type*.

[`PerformanceObserverEntryList.getEntriesByName()`](performanceobserverentrylist/getentriesbyname)  
Returns a list of explicitly *observed* [`PerformanceEntry`](performanceentry) objects based on the given *name* and *entry type*.

Example
-------

    // Create observer for all performance event types
    // list is of type PerformanceObserveEntryList
    var observe_all = new PerformanceObserver(function(list, obs) {
       var perfEntries = list.getEntries();
       for (var i = 0; i < perfEntries.length; i++) {
          print_perf_entry(perfEntries[i]);
          // do something with it
       }
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#idl-def-performanceobserverentrylist">Performance Timeline Level 2<br />
<span class="small">The definition of 'PerformanceObserverEntryList' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PerformanceObserverEntryList`

52

≤79

57

No

39

11

No

52

57

41

11

6.0

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

`getEntriesByName`

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

`getEntriesByType`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserverEntryList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserverEntryList</a>
