PerformanceResourceTiming.workerStart
=====================================

The `workerStart` read-only property of the [`PerformanceResourceTiming`](../performanceresourcetiming) interface returns a [`DOMHighResTimeStamp`](../domhighrestimestamp) immediately before dispatching the [`FetchEvent`](../fetchevent) if a Service Worker thread is already running, or immediately before starting the Service Worker thread if it is not already running. If the resource is not intercepted by a Service Worker the property will always return 0.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    resource.workerStart;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp).

Example
-------

In the following example, the value of the `*Start` and `*End` properties of all "`resource`" [`type`](../performanceentry/entrytype) events are logged.

    function print_PerformanceEntries() {
      // Use getEntriesByType() to just get the "resource" events
      var p = performance.getEntriesByType("resource");
      for (var i=0; i < p.length; i++) {
        print_start_and_end_properties(p[i]);
      }
    }
    function print_start_and_end_properties(perfEntry) {
      // Print timestamps of the PerformanceEntry *start and *end properties
      properties = ["connectStart", "connectEnd",
                    "domainLookupStart", "domainLookupEnd",
                    "fetchStart",
                    "redirectStart", "redirectEnd",
                    "requestStart",
                    "responseStart", "responseEnd",
                    "secureConnectionStart",
            "workerStart"];

      for (var i=0; i < properties.length; i++) {
        // check each property
        var supported = properties[i] in perfEntry;
        if (supported) {
          var value = perfEntry[properties[i]];
          console.log("... " + properties[i] + " = " + value);
        } else {
          console.log("... " + properties[i] + " = NOT supported");
        }
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-2/#dom-performanceresourcetiming-workerstart">Resource Timing Level 2<br />
<span class="small">The definition of 'workerStart' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`workerStart`

43

16

58

No

32

11

43

43

58

32

11

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/workerStart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/workerStart</a>
