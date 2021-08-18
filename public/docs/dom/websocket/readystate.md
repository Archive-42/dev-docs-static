WebSocket.readyState
====================

The `WebSocket.readyState` read-only property returns the current state of the [`WebSocket`](../websocket) connection.

Syntax
------

    var readyState = aWebSocket.readyState;

Value
-----

One of the following `unsigned short` values:

<table><thead><tr class="header"><th>Value</th><th>State</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>0</code></td><td><code>CONNECTING</code></td><td>Socket has been created. The connection is not yet open.</td></tr><tr class="even"><td><code>1</code></td><td><code>OPEN</code></td><td>The connection is open and ready to communicate.</td></tr><tr class="odd"><td><code>2</code></td><td><code>CLOSING</code></td><td>The connection is in the process of closing.</td></tr><tr class="even"><td><code>3</code></td><td><code>CLOSED</code></td><td>The connection is closed or couldn't be opened.</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-websocket-readystate">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket: readyState' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`readyState`

43

12

19

10

30

10

43

43

19

30

10

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/readyState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/readyState</a>
