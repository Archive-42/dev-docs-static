WebSocket()
===========

The `WebSocket()` constructor returns a new [`WebSocket`](../websocket) object.

Syntax
------

    var aWebSocket = new WebSocket(url [, protocols]);

### Parameters

`url`  
The URL to which to connect; this should be the URL to which the WebSocket server will respond.

 `protocols` <span class="badge inline optional">Optional</span>   
Either a single protocol string or an array of protocol strings. These strings are used to indicate sub-protocols, so that a single server can implement multiple WebSocket sub-protocols (for example, you might want one server to be able to handle different types of interactions depending on the specified `protocol`).

If it is omitted, an empty array is used by default, i.e. `[]`.

### Exceptions thrown

`SECURITY_ERR`  
The port to which the connection is being attempted is being blocked.

 [SyntaxError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError)   
The URL is invalid.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-websocket">HTML Living Standard<br />
<span class="small">The definition of 'the WebSocket constructor' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`WebSocket`

Yes

12

7

4-7

Parameter `protocols` not supported.

10

Yes

Yes

Yes

Yes

7

?

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/WebSocket" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/WebSocket</a>
