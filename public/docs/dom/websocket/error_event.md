WebSocket: error event
======================

The `error` event is fired when a connection with a `WebSocket` has been closed due to an error (some data couldn't be sent for example).

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onerror"><code>onerror</code></a></td></tr></tbody></table>

Examples
--------

    // Create WebSocket connection
    const socket = new WebSocket('ws://localhost:8080');

    // Listen for possible errors
    socket.addEventListener('error', function (event) {
      console.log('WebSocket error: ', event);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-sockets.html#event-error">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket error' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`error_event`

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
-   [WebSocket: message event](message_event)
-   [WebSocket: open event](open_event)
-   [Writing WebSocket client applications](../websockets_api/writing_websocket_client_applications)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/error_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/error_event</a>
