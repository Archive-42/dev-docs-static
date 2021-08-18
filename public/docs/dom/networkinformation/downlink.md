# NetworkInformation.downlink

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `downlink` read-only property of the [`NetworkInformation`](../networkinformation) interface returns the effective bandwidth estimate in megabits per second, rounded to the nearest multiple of 25 kilobits per seconds. This value is based on recently observed application layer throughput across recently active connections, excluding connections made to a private address space. In the absence of recent bandwidth measurement data, the attribute value is determined by the properties of the underlying connection technology.

Note that Chrome-based browsers do not conform to the specification, and [arbitrarily cap](https://source.chromium.org/chromium/chromium/src/+/master:third_party/blink/renderer/platform/network/network_state_notifier.cc;l=460;drc=49bf35554c123bbc44a0ef52675144eba2dd7bbc?originalUrl=https:%2F%2Fcs.chromium.org%2F) the reported downlink at a maximum of 10 Mbps as an anti-fingerprinting measure. Similar caps exist for the reported latency.

## Syntax

    var downLink = NetworkInformation.downlink

### Value

A <span class="page-not-created">`double`</span>.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/netinfo/#dom-networkinformation-downlink">Network Information API<br />
<span class="small">The definition of 'downlink' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`downlink`

61

79

No

No

48

No

50

38

?

45

No

3.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/downlink" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/downlink</a>
