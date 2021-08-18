WebSocket.onclose
=================

The `WebSocket.onclose` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that is called when the WebSocket connection's [`readyState`](readystate) changes to [`CLOSED`](readystate). It is called with a [`CloseEvent`](../closeevent).

Syntax
------

    aWebSocket.onclose = function(event) {
      console.log("WebSocket is closed now.");
    };

Value
-----

An [`EventListener`](../eventlistener).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-websocket-onclose">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket: onclose' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/onclose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/onclose</a>
