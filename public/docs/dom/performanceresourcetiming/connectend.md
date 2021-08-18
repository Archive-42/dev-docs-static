PerformanceResourceTiming.connectEnd
====================================

The `connectEnd` read-only property returns the [`timestamp`](../domhighrestimestamp) immediately after the browser finishes establishing the connection to the server to retrieve the resource. The timestamp value includes the time interval to establish the transport connection, as well as other time intervals such as SSL handshake and SOCKS authentication.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    resource.connectEnd;

### Return value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) representing the time after a connection is established.

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
      // Print timestamps of the *start and *end properties
      properties = ["connectStart", "connectEnd",
                    "domainLookupStart", "domainLookupEnd",
                    "fetchStart",
                    "redirectStart", "redirectEnd",
                    "requestStart",
                    "responseStart", "responseEnd",
                    "secureConnectionStart"];

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-1/#dom-performanceresourcetiming-connectend">Resource Timing Level 1<br />
<span class="small">The definition of 'connectEnd' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`connectEnd`

43

12

40

10

32

11

43

43

42

32

11

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/connectEnd" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/connectEnd</a>
