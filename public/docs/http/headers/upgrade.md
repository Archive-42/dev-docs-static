Upgrade
=======

The HTTP 1.1 (only) `Upgrade` header can be used to upgrade an already established client/server connection to a different protocol (over the same transport protocol). For example, it can be used by a client to upgrade a connection from HTTP 1.1 to HTTP 2.0, or an HTTP or HTTPS connection into a WebSocket.

HTTP/2 explicitly disallows the use of this mechanism/header; it is specific to HTTP/1.1.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/General_header">General header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Overview
--------

The `Upgrade` header field may be used by clients to invite a server to switch to one (or more) of the listed protocols, in descending preference order.

For example, the client might send a `GET` request as shown, listing the preferred protocols to switch to (in this case "example/1" and "foo/2"):

    GET /index.html HTTP/1.1
    Host: www.example.com
    Connection: upgrade
    Upgrade: example/1, foo/2

**Note**: `Connection: upgrade` must be set whenever `Upgrade` is sent.

The server can choose to ignore the request, for any reason, in which case it should just respond as though the `Upgrade` header had not been sent (for example, with a [`200 OK`](../status/200)).

If the server decides to upgrade the connection, it must:

1.  Send back a [`101 Switching Protocols`](../status/101) response status with an `Upgrade` header that specifies the protocol(s) being switched to. For example:

        HTTP/1.1 101 Switching Protocols
        Upgrade: foo/2
        Connection: Upgrade

2.  Send a response to the original request *using the new protocol* (the server may only switch to a protocol with which it can complete the original request).

A server may also send the header as part of a [`426`](../status/426) `Upgrade Required` response, to indicate that the server won't perform the request using the current protocol, but might do so if the protocol is changed. The client can then request a protocol change using the process above.

More detail and examples are provided in the topic [Protocol upgrade mechanism](../protocol_upgrade_mechanism).

Syntax
------

    Connection: upgrade
    Upgrade: protocol_name[/protocol_version]

Notes:

-   The [`Connection`](connection) header with type `upgrade` must *always* be sent with the `Upgrade` header (as shown above).
-   Protocols are listed, comma-separated, in order of descending preference. Protocol version is optional. For example:

          Connection: upgrade
          Upgrade: a_protocol/1, example ,another_protocol/2.2

Directives
----------

any comma-separated list protocol names (each with optional protocol version)  
One or more protocol names with optional version ("/" separated). The protocols are listed in order of descending preference.

Examples
--------

    Connection: upgrade
    Upgrade: HTTP/2.0, SHTTP/1.3, IRC/6.9, RTA/x11

    Connection: Upgrade
    Upgrade: websocket

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7230#section-6.7">RFC 7230, section 6.7: Hypertext Transfer Protocol (HTTP/1.1): Message Syntax and Routing</a></td><td>IETF RFC</td><td></td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc7231#section-6.5.15">RFC 7231, section 6.5.15: 426 Upgrade Required</a></td><td>IETF RFC</td><td></td></tr><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7540#section-8.1.1">RFC 7540, section 8.1.1: Hypertext Transfer Protocol Version 2 (HTTP/2)</a></td><td>IETF RFC</td><td></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found. Please contribute data for "http.headers.Upgrade" (depth: 1) to the [MDN compatibility data repository](https://github.com/mdn/browser-compat-data).

See also
--------

-   [Protocol upgrade mechanism](../protocol_upgrade_mechanism)
-   [`101`](../status/101) `Switching Protocol`
-   [`426`](../status/426) `Upgrade Required`
-   [`Connection`](connection)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Upgrade$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Upgrade" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Upgrade</a>
