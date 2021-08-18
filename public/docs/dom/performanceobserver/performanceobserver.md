PerformanceObserver()
=====================

The `PerformanceObserver()` constructor creates a new [`PerformanceObserver`](../performanceobserver) object with the given observer `callback`. The observer callback is invoked when [performance entry events](../performanceentry) are recorded for the [entry types](../performanceentry/entrytype) that have been registered, via the [`observe()`](observe) method.

Syntax
------

    var observer = new PerformanceObserver(callback);

### Parameters

*`callback`*  
A `PerformanceObserverCallback` callback that will be invoked when *observed* performance events are recorded. When the callback is invoked, its first parameter is a [list of performance observer entries](../performanceobserverentrylist) and the second parameter is the [`observer`](../performanceobserver) object.

### Return value

A new [`PerformanceObserver`](../performanceobserver) object which will call the specified `callback` when observed performance events occur.

Example
-------

    var observer = new PerformanceObserver(function(list, obj) {
      var entries = list.getEntries();
      for (var i=0; i < entries.length; i++) {
        // Process "mark" and "frame" events
      }
    });
    observer.observe({entryTypes: ["mark", "frame"]});

    function perf_observer(list, observer) {
      // Process the "measure" event
    }
    var observer2 = new PerformanceObserver(perf_observer);
    observer2.observe({entryTypes: ["measure"]});

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#idl-def-performanceobservercallback">Performance Timeline Level 2<br />
<span class="small">The definition of 'PerformanceObserver()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition of <code>PerformanceObserver()</code> constructor.</td></tr></tbody></table>

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

`PerformanceObserver`

52

≤79

57

No

39

11

52

52

57

41

11

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver/PerformanceObserver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver/PerformanceObserver</a>
