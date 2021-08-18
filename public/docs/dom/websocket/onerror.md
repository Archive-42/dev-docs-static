WebSocket.onerror
=================

The [`WebSocket`](../websocket) interface's `onerror` event handler property is a function which gets called when an error occurs on the WebSocket.

You can also add an `error` event handler using [`addEventListener()`](../eventtarget/addeventlistener).

Syntax
------

    webSocket.onerror = eventHandler;

### Value

A function or [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which is executed whenever an `error` event occurs on the WebSocket connection.

Example
-------

    webSocket.onerror = function(event) {
      console.error("WebSocket error observed:", event);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-websocket-onerror">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket: onerror' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`onerror`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/onerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/onerror</a>
