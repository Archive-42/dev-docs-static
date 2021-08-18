# PerformanceResourceTiming.nextHopProtocol

The `nextHopProtocol` read-only property is a [`string`](../domstring) representing the _network protocol_ used to fetch the resource, as identified by the [ALPN Protocol ID (RFC7301)](https://datatracker.ietf.org/doc/html/rfc7301).

When a proxy is used, if a tunnel connection is established, this property returns the ALPN Protocol ID of the tunneled protocol. Otherwise, this property returns the ALPN Protocol ID of the first hop to the proxy.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    resource.nextHopProtocol;

### Return value

A [`string`](../domstring) representing the _network protocol_ used to fetch the resource, as identified by the [ALPN Protocol ID (RFC7301)](https://datatracker.ietf.org/doc/html/rfc7301).

## Example

The following example uses the `nextHopProtocol` property.

    function print_PerformanceEntries() {
      // Use getEntriesByType() to just get the "resource" events
      var p = performance.getEntriesByType("resource");
      for (var i=0; i < p.length; i++) {
        print_nextHopProtocol(p[i]);
      }
    }
    function print_nextHopProtocol(perfEntry) {
      var value = "nextHopProtocol" in perfEntry;
      if (value)
        console.log("nextHopProtocol = " + perfEntry.nextHopProtocol);
      else
        console.log("nextHopProtocol = NOT supported");
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-2/#dom-performanceresourcetiming-nexthopprotocol">Resource Timing Level 2<br />
<span class="small">The definition of 'nextHopProtocol' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`nextHopProtocol`

61

17

45

No

No

No

61

61

45

No

No

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/nextHopProtocol" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/nextHopProtocol</a>
