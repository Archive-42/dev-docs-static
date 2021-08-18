RTCDataChannel.onclosing
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `RTCDataChannel.onclosing` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function to be called by the browser when the `closing` event is received by the [`RTCDataChannel`](../rtcdatachannel). This is a simple [`Event`](../event) which indicates that the data channel is being closed, that is, [`RTCDataChannel`](../rtcdatachannel) transitions to "closing" state. For example, after [`RTCDataChannel.close()`](close) was called but the underlying data transport might not have been closed yet.

Syntax
------

    RTCDataChannel.onclosing = function;

### Value

A function which the browser will call to handle the `closing` event. The function receives as its sole input parameter the event itself, as an object of type [`Event`](../event).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdatachannel-onclosing">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.onclosing' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onclosing`

81

81

No

No

68

No

81

81

No

?

No

13.0

See also
--------

-   [WebRTC](../webrtc_api)
-   [`RTCDataChannel.onclose`](onclose) event handler and its `close` event.
-   [`RTCDataChannel.onopen`](onopen)
-   The `open` event and its type, [`Event`](../event).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onclosing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onclosing</a>
