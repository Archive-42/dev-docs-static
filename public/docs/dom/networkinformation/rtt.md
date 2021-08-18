NetworkInformation.rtt
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `NetworkInformation.rtt` read-only property returns the estimated effective round-trip time of the current connection, rounded to the nearest multiple of 25 milliseconds. This value is based on recently observed application-layer RTT measurements across recently active connections. It excludes connections made to a private address space. If no recent measurement data is available, the value is based on the properties of the underlying connection technology.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    rtt = NetworkInformation.rtt

### Return value

A number.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/netinfo/#dom-networkinformation-rtt">Network Information API<br />
<span class="small">The definition of 'rtt' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`rtt`

61

79

No

No

48

No

50

38

No

45

No

3.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/rtt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/rtt</a>
