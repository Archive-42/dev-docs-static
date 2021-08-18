WebSocket: close event
======================

The `close` event is fired when a connection with a `WebSocket` is closed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../closeevent"><code>CloseEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onclose"><code>onclose</code></a></td></tr></tbody></table>

Examples
--------

You might want to know when the connection has been closed so that you can update the UI or, perhaps, save data about the closed connection. Given that you have a variable called `exampleSocket` that refers to an opened `WebSocket`, this handler would handle the situation where the socket has been closed.

    exampleSocket.addEventListener('close', (event) => {
      console.log('The connection has been closed successfully.');
    });

You can perform the same actions using the event handler property, like this:

    exampleSocket.onclose = function (event) {
      console.log('The connection has been closed successfully.');
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-sockets.html#event-close">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket close' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`close_event`

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

-   [WebSocket: error event](error_event)
-   [WebSocket: message event](message_event)
-   [WebSocket: open event](open_event)
-   [Writing WebSocket client applications](../websockets_api/writing_websocket_client_applications)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/close_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/close_event</a>
