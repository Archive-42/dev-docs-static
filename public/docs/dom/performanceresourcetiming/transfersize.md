# PerformanceResourceTiming.transferSize

The `transferSize` read-only property represents the size (in octets) of the fetched resource. The size includes the response header fields plus the response payload body (as defined by [RFC7230](https://httpwg.github.io/specs/rfc7230.html#message.body)).

**Note:** This feature is available in [Web Workers](../web_workers_api).

If the resource is fetched from a local cache, or if it is a cross-origin resource, this property returns zero.

## Syntax

    resource.transferSize;

### Return value

A `number` representing the size (in octets) of the fetched resource. The size includes the response header fields plus the [response payload body](https://httpwg.github.io/specs/rfc7230.html#message.body) (RFC7230).

## Example

The following example, the value of size properties of all "`resource`" [`type`](../performanceentry/entrytype) events are logged.

    function log_sizes(perfEntry){
      // Check for support of the PerformanceEntry.*size properties and print their values
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-2/#dom-performanceresourcetiming-transfersize">Resource Timing Level 2<br />
<span class="small">The definition of 'transferSize' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`transferSize`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/transferSize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/transferSize</a>
