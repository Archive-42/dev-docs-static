WebSocket.onmessage
===================

The `WebSocket.onmessage` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that is called when a message is received from the server. It is called with a [`MessageEvent`](../messageevent).

Syntax
------

    aWebSocket.onmessage = function(event) {
      console.debug("WebSocket message received:", event);
    };

Value
-----

An [`EventListener`](../eventlistener).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-websocket-onmessage">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket: onmessage' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`onmessage`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/onmessage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/onmessage</a>
