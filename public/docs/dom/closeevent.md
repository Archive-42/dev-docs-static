# CloseEvent

A `CloseEvent` is sent to clients using [WebSockets](https://developer.mozilla.org/en-US/docs/Glossary/WebSockets) when the connection is closed. This is delivered to the listener indicated by the `WebSocket` object's `onclose` attribute.

## Constructor

[`CloseEvent()`](closeevent/closeevent)  
Creates a new `CloseEvent`.

## Properties

_This interface also inherits properties from its parent, [`Event`](event)._

<span class="page-not-created">`CloseEvent.code`</span> <span class="badge inline readonly">Read only </span>  
Returns an `unsigned short` containing the close code sent by the server. The following values are permitted status codes. The following definitions are sourced from the IANA website \[[Ref](https://www.iana.org/assignments/websocket/websocket.xml#close-code-number)\]. Note that the 1xxx codes are only WebSocket-internal and not for the same meaning by the transported data (like when the application-layer protocol is invalid). The only permitted codes to be specified in Firefox are 1000 and 3000 to 4999 \[[Source](https://searchfox.org/mozilla-central/rev/bf81d741ff5dd11bb364ef21306da599032fd479/dom/websocket/WebSocket.cpp#2533), [Bug](https://bugzilla.mozilla.org/show_bug.cgi?id=1467107)\].

<table><thead><tr class="header"><th>Status code</th><th>Name</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>0</code>–<code>999</code></td><td></td><td><strong>Reserved and not used.</strong></td></tr><tr class="even"><td><code>1000</code></td><td>Normal Closure</td><td>Normal closure; the connection successfully completed whatever purpose for which it was created.</td></tr><tr class="odd"><td><code>1001</code></td><td>Going Away</td><td>The endpoint is going away, either because of a server failure or because the browser is navigating away from the page that opened the connection.</td></tr><tr class="even"><td><code>1002</code></td><td>Protocol Error</td><td>The endpoint is terminating the connection due to a protocol error.</td></tr><tr class="odd"><td><code>1003</code></td><td>Unsupported Data</td><td>The connection is being terminated because the endpoint received data of a type it cannot accept (for example, a text-only endpoint received binary data).</td></tr><tr class="even"><td><code>1004</code></td><td></td><td><strong>Reserved.</strong> A meaning might be defined in the future.</td></tr><tr class="odd"><td><code>1005</code></td><td>No Status Received</td><td><strong>Reserved.</strong> Indicates that no status code was provided even though one was expected.</td></tr><tr class="even"><td><code>1006</code></td><td>Abnormal Closure</td><td><strong>Reserved.</strong> Used to indicate that a connection was closed abnormally (that is, with no close frame being sent) when a status code is expected.</td></tr><tr class="odd"><td><code>1007</code></td><td>Invalid frame payload data</td><td>The endpoint is terminating the connection because a message was received that contained inconsistent data (e.g., non-UTF-8 data within a text message).</td></tr><tr class="even"><td><code>1008</code></td><td>Policy Violation</td><td>The endpoint is terminating the connection because it received a message that violates its policy. This is a generic status code, used when codes 1003 and 1009 are not suitable.</td></tr><tr class="odd"><td><code>1009</code></td><td>Message too big</td><td>The endpoint is terminating the connection because a data frame was received that is too large.</td></tr><tr class="even"><td><code>1010</code></td><td>Missing Extension</td><td>The client is terminating the connection because it expected the server to negotiate one or more extension, but the server didn't.</td></tr><tr class="odd"><td><code>1011</code></td><td>Internal Error</td><td>The server is terminating the connection because it encountered an unexpected condition that prevented it from fulfilling the request.</td></tr><tr class="even"><td><code>1012</code></td><td>Service Restart</td><td>The server is terminating the connection because it is restarting. [<a href="https://www.ietf.org/mail-archive/web/hybi/current/msg09670.html">Ref</a>]</td></tr><tr class="odd"><td><code>1013</code></td><td>Try Again Later</td><td>The server is terminating the connection due to a temporary condition, e.g. it is overloaded and is casting off some of its clients. [<a href="https://www.ietf.org/mail-archive/web/hybi/current/msg09670.html">Ref</a>]</td></tr><tr class="even"><td><code>1014</code></td><td>Bad Gateway</td><td>The server was acting as a gateway or proxy and received an invalid response from the upstream server. This is similar to 502 HTTP Status Code.</td></tr><tr class="odd"><td><code>1015</code></td><td>TLS Handshake</td><td><strong>Reserved.</strong> Indicates that the connection was closed due to a failure to perform a TLS handshake (e.g., the server certificate can't be verified).</td></tr><tr class="even"><td><code>1016</code>–<code>1999</code></td><td></td><td><strong>Reserved for future use by the WebSocket standard.</strong></td></tr><tr class="odd"><td><code>2000</code>–<code>2999</code></td><td></td><td><strong>Reserved for use by WebSocket extensions.</strong></td></tr><tr class="even"><td><code>3000</code>–<code>3999</code></td><td></td><td>Available for use by libraries and frameworks. <strong>May not</strong> be used by applications. Available for registration at the IANA via first-come, first-serve.</td></tr><tr class="odd"><td><code>4000</code>–<code>4999</code></td><td></td><td>Available for use by applications.</td></tr></tbody></table>

<span class="page-not-created">`CloseEvent.reason`</span> <span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) indicating the reason the server closed the connection. This is specific to the particular server and sub-protocol.

<span class="page-not-created">`CloseEvent.wasClean`</span> <span class="badge inline readonly">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that Indicates whether or not the connection was cleanly closed.

## Methods

_This interface also inherits methods from its parent, [`Event`](event)._

[`CloseEvent.initCloseEvent()`](closeevent/initcloseevent) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Initializes the value of a `CloseEvent` created. If the event has already being dispatched, this method does nothing. Do not use this method anymore, use the [`CloseEvent()`](closeevent/closeevent) constructor instead.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-sockets.html#the-closeevent-interface">HTML Living Standard<br />
<span class="small">The definition of 'CloseEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`CloseEvent`

13

12

8

\["Prior to Firefox 12, the close code `CLOSE_NORMAL` was used when the channel was closed due to an unexpected error or unspecified error condition.", "Prior to Firefox 8, the `WebSocket` close event was sent to the listener as a simple event."\]

10

12.1

6

≤37

18

8

12.1

6

1.0

`CloseEvent`

?

?

8

?

?

Yes

?

?

8

?

Yes

?

`initCloseEvent`

No

12-79

8-41

No

No

No

No

No

8-41

No

No

No

## See also

- [`WebSocket`](websocket)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CloseEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CloseEvent</a>
