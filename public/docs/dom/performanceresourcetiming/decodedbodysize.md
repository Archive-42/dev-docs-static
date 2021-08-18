# PerformanceResourceTiming.decodedBodySize

The `decodedBodySize` read-only property returns the size (in octets) received from the fetch (HTTP or cache) of the message body, after removing any applied content-codings. If the resource is retrieved from an application cache or local resources, it returns the size of the payload after removing any applied content-codings.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    resource.decodedBodySize;

### Return value

The size (in octets) received from the fetch (HTTP or cache) of the message body, after removing any applied content-codings.

## Example

The following example, the value of the size properties of all "`resource`" [`type`](../performanceentry/entrytype) events are logged.

    function log_sizes(perfEntry){
      // Check for support of the *size properties and print their values
      // if supported.
      if ("decodedBodySize" in perfEntry)
        console.log("decodedBodySize = " + perfEntry.decodedBodySize);
      else
        console.log("decodedBodySize = NOT supported");

      if ("encodedBodySize" in perfEntry)
        console.log("encodedBodySize = " + perfEntry.encodedBodySize);
      else
        console.log("encodedBodySize = NOT supported");

      if ("transferSize" in perfEntry)
        console.log("transferSize = " + perfEntry.transferSize);
      else
        console.log("transferSize = NOT supported");
    }
    function check_PerformanceEntries() {
      // Use getEntriesByType() to just get the "resource" events
      var p = performance.getEntriesByType("resource");
      for (var i=0; i < p.length; i++) {
        log_sizes(p[i]);
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-2/#dom-performanceresourcetiming-decodedbodysize">Resource Timing Level 2<br />
<span class="small">The definition of 'decodedBodySize' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`decodedBodySize`

54

17

45

No

41

No

54

54

45

41

No

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/decodedBodySize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/decodedBodySize</a>
