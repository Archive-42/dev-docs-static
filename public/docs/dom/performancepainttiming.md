PerformancePaintTiming
======================

The `PerformancePaintTiming` interface of the [Paint Timing API](paint_timing_api) provides timing information about "paint" (also called "render") operations during web page construction. "Paint" refers to conversion of the render tree to on-screen pixels.

An application can register a [`PerformanceObserver`](performanceobserver) for "`paint`" [`performance entry types`](performanceentry) and the observer can retrieve the times that paint events occur. Use this information to help identify areas that take too long to provide a good user experience.

Properties
----------

This interface has no properties but it extends the following [`PerformanceEntry`](performanceentry) properties (for "`paint`" [`performance entry types`](performanceentry/entrytype)) by qualifying and constraining the properties as follows:

[`PerformanceEntry.entryType`](performanceentry/entrytype)  
Returns "`paint`".

[`PerformanceEntry.name`](performanceentry/name)  
Returns either `"first-paint"` or `"first-contentful-paint"`.

[`PerformanceEntry.startTime`](performanceentry/starttime)  
Returns the [`timestamp`](domhighrestimestamp) when the paint occurred.

[`PerformanceEntry.duration`](performanceentry/duration)  
Returns 0.

Methods
-------

This interface has no methods.

Example
-------

    function showPaintTimings() {
      if (window.performance) {
        let performance = window.performance;
        let performanceEntries = performance.getEntriesByType('paint');
        performanceEntries.forEach( (performanceEntry, i, entries) => {
          console.log("The time to " + performanceEntry.name + " was " + performanceEntry.startTime + " milliseconds.");
        });
      } else {
        console.log('Performance timing isn\'t supported.');
      }
    }

The code above produces console output something like the following:

    The time to first-paint was 2785.915 milliseconds.
    The time to first-contentful-paint was 2787.460 milliseconds.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/paint-timing/#sec-PerformancePaintTiming">Paint Timing<br />
<span class="small">The definition of 'PerformancePaintTiming' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PerformancePaintTiming`

60

≤79

84

No

47

14.1

60

60

84

44

14.5

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformancePaintTiming" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformancePaintTiming</a>
