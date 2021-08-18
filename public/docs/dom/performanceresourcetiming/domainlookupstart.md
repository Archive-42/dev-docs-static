# PerformanceResourceTiming.domainLookupStart

The `domainLookupStart` read-only property returns the [`timestamp`](../domhighrestimestamp) immediately before the browser starts the domain name lookup for the resource.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    resource.domainLookupStart;

### Return value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) immediately before the browser starts the domain name lookup for the resource.

## Example

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-1/#dom-performanceresourcetiming-domainlookupstart">Resource Timing Level 1<br />
<span class="small">The definition of 'domainLookupStart' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`domainLookupStart`

43

12

40

No

30

11

43

43

42

30

11

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/domainLookupStart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/domainLookupStart</a>
