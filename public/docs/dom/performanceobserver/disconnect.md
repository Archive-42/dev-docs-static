PeformanceObserver.disconnect()
===============================

The `disconnect()` method of the [`PerformanceObserver`](../performanceobserver) interface is used to stop the performance observer from receiving any [performance entry](../performanceentry) events.

Syntax
------

    performanceObserver.disconnect();

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
      // ...
      // Disable additional performance events
      observer.disconnect();
    }
    var observer2 = new PerformanceObserver(perf_observer);
    observer2.observe({entryTypes: ["measure"]});

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performanceobserver-disconnect">Performance Timeline Level 2<br />
<span class="small">The definition of 'disconnect()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition of <code>disconnect()</code> method.</td></tr></tbody></table>

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

`disconnect`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver/disconnect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver/disconnect</a>
