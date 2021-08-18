WebSocket.bufferedAmount
========================

The `WebSocket.bufferedAmount` read-only property returns the number of bytes of data that have been queued using calls to `send()` but not yet transmitted to the network. This value resets to zero once all queued data has been sent. This value does not reset to zero when the connection is closed; if you keep calling `send()`, this will continue to climb.

Syntax
------

    var bufferedAmount = aWebSocket.bufferedAmount;

Value
-----

An `unsigned long`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-websocket-bufferedamount">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket: bufferedAmount' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`bufferedAmount`

Yes

12

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/bufferedAmount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/bufferedAmount</a>
