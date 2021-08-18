RTCSctpTransport.state
======================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `state` read-only property of the [`RTCSctpTransport`](../rtcsctptransport) interface provides information which describes a Stream Control Transmission Protocol (**[SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP)**) transport state.

Syntax
------

    var myState = sctpTransport.state;

### Value

A string whose value is taken from the `RTCSctpTransportState` enumerated type. Its value is one of the following:

`connecting`  
The initial state when the connection is being estabilished.

`connected`  
The connection is open for data transmission.

`closed`  
The connection is closed and can no longer be used.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcsctptransport-state">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCSctpTransport.state' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`state`

76

79

No

See [bug 1278299](https://bugzil.la/1278299).

No

No

No

76

76

No

See [bug 1278299](https://bugzil.la/1278299).

54

No

12.0

See also
--------

-   [`RTCSctpTransport`](../rtcsctptransport)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport/state" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport/state</a>
