WebSocket: open event
=====================

The `open` event is fired when a connection with a `WebSocket` is opened.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onopen"><code>onopen</code></a></td></tr></tbody></table>

Examples
--------

    // Create WebSocket connection.
    const socket = new WebSocket('ws://localhost:8080');

    // Connection opened
    socket.addEventListener('open', (event) => {
      socket.send('Hello Server!');
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-sockets.html#event-open">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket open' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`open_event`

Yes

12

Yes

?

Yes

?

Yes

Yes

Yes

?

?

Yes

See also
--------

-   [WebSocket: close event](close_event)
-   [WebSocket: error event](error_event)
-   [WebSocket: message event](message_event)
-   [Writing WebSocket client applications](../websockets_api/writing_websocket_client_applications)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/open_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/open_event</a>
