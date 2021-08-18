WebSocket.onopen
================

The `WebSocket.onopen` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that is called when the [`WebSocket`](../websocket) connection's [`readyState`](readystate) changes to [`1`](readystate); this indicates that the connection is ready to send and receive data. It is called with an [`Event`](../event).

Syntax
------

    aWebSocket.onopen = function(event) {
      console.log("WebSocket is open now.");
    };

Value
-----

An [`EventListener`](../eventlistener).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-websocket-onopen">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket: onopen' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`onopen`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/onopen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/onopen</a>
