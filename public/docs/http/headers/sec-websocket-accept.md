Sec-WebSocket-Accept
====================

**Draft**  
This page is not complete.

The **Sec-WebSocket-Accept** header is used in the websocket opening handshake. It would appear in the response headers. That is, this is header is sent from server to client to inform that server is willing to initiate a websocket connection.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Sec-WebSocket-Accept: <hashed key>

Directives
----------

&lt;hashed key&gt;  
The server takes the value of the Sec-WebSocket-Key sent in the handshake request, appends `258EAFA5-E914-47DA-95CA-C5AB0DC85B11`, takes SHA-1 of the new value, and is then [base64](https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64/Base64_encoding_and_decoding) encoded.

Examples
--------

    Sec-WebSocket-Accept: s3pPLMBiTxaQ9kYGzzhZRbK+xOo=

Specification
-------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc6455#section-11.3.3">RFC 6455, section 11.3.3: Sec-WebSocket-Accept</a></td><td>The WebSocket Protocol</td></tr></tbody></table>

See also
--------

-   [`Sec-WebSocket-Key`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-WebSocket-Key)

Browser compatibility
---------------------

No compatibility data found. Please contribute data for "http.headers.Sec-WebSocket-Accept" (depth: 1) to the [MDN compatibility data repository](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-WebSocket-Accept$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-WebSocket-Accept" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-WebSocket-Accept</a>
