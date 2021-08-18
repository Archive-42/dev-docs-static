The WebSocket API (WebSockets)
==============================

The **WebSocket API** is an advanced technology that makes it possible to open a two-way interactive communication session between the user's browser and a server. With this API, you can send messages to a server and receive event-driven responses without having to poll the server for a reply.

**Note:** While a WebSocket connection is functionally somewhat similar to standard Unix-style sockets, they are not related.

Interfaces
----------

[`WebSocket`](websocket)  
The primary interface for connecting to a WebSocket server and then sending and receiving data on the connection.

`CloseEvent`  
The event sent by the WebSocket object when the connection closes.

[`MessageEvent`](messageevent)  
The event sent by the WebSocket object when a message is received from the server.

Guides
------

-   [Writing WebSocket client applications](websockets_api/writing_websocket_client_applications)
-   [Writing WebSocket servers](websockets_api/writing_websocket_servers)
-   [Writing a WebSocket server in C\#](websockets_api/writing_websocket_server)
-   [Writing a WebSocket server in Java](websockets_api/writing_a_websocket_server_in_java)

Tools
-----

-   [HumbleNet](https://hacks.mozilla.org/2017/06/introducing-humblenet-a-cross-platform-networking-library-that-works-in-the-browser/): A cross-platform networking library that works in the browser. It consists of a C wrapper around WebSockets and WebRTC that abstracts away cross-browser differences, facilitating the creation of multi-user networking functionality for games and other apps.
-   [µWebSockets](https://github.com/uWebSockets/uWebSockets): Highly scalable WebSocket server and client implementation for [C++11](https://isocpp.org/) and [Node.js](https://nodejs.org).
-   [ClusterWS](https://github.com/ClusterWS/ClusterWS): Lightweight, fast and powerful framework for building scalable WebSocket applications in [Node.js](https://nodejs.org).
-   [CWS](https://github.com/ClusterWS/cWS): Fast C++ WebSocket implementation for Node.js (uWebSockets v0.14 fork)
-   [Socket.IO](https://socket.io): A long polling/WebSocket based third party transfer protocol for [Node.js](https://nodejs.org).
-   [SocketCluster](https://socketcluster.io/): A pub/sub WebSocket framework for [Node.js](https://nodejs.org) with a focus on scalability.
-   [WebSocket-Node](https://github.com/Worlize/WebSocket-Node): A WebSocket server API implementation for [Node.js](https://nodejs.org).
-   [Total.js](https://www.totaljs.com): Web application framework for [Node.js](https://www.nodejs.org) (Example: [WebSocket chat](https://github.com/totaljs/examples/tree/master/websocket))
-   [Faye](https://www.npmjs.com/package/faye-websocket): A [WebSocket](websockets_api) (two-ways connections) and [EventSource](eventsource) (one-way connections) for [Node.js](https://nodejs.org) Server and Client.
-   [SignalR](https://signalr.net/): SignalR will use WebSockets under the covers when it's available, and gracefully fallback to other techniques and technologies when it isn't, while your application code stays the same.
-   [Caddy](https://caddyserver.com/docs/websocket): A web server capable of proxying arbitrary commands (stdin/stdout) as a websocket.
-   [ws](https://github.com/websockets/ws): a popular WebSocket client & server library for [Node.js](https://nodejs.org/).
-   [jsonrpc-bidirectional](https://github.com/bigstepinc/jsonrpc-bidirectional): Asynchronous RPC which, on a single connection, may have functions exported on the server and, and the same time, on the client (client may call server, server may also call client).
-   [cowboy](https://github.com/ninenines/cowboy): Cowboy is a small, fast and modern HTTP server for Erlang/OTP with WebSocket support.
-   [WebSocket King](https://websocketking.com): A client tool to help develop, test and work with WebSocket servers.
-   [PHP WebSocket Server](https://github.com/napengam/phpWebSocketServer):Server written in PHP to handle connections via websocksets wss:// or ws://and normal sockets over ssl:// ,tcp://

Related Topics
--------------

-   [AJAX](https://developer.mozilla.org/en-US/docs/Web/Guide/AJAX)
-   [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-sockets.html">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket API' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/websockets/">WebSockets</a></td><td><span class="spec-CR">Candidate Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc6455">RFC 6455: The WebSocket Protocol</a></td><td><span class="spec-RFC">IETF RFC</span></td><td></td></tr></tbody></table>

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

`WebSockets_API`

4

12

11

7-11

Message size limited to 16 MB (see [bug 711205](https://bugzil.la/711205)).

4-6

Message size limited to 16 MB (see [bug 711205](https://bugzil.la/711205)).

10

12.1

5

≤37

18

14

See [bug 695635](https://bugzil.la/695635).

7-14

Message size limited to 16 MB (see [bug 711205](https://bugzil.la/711205)).

4-6

Message size limited to 16 MB (see [bug 711205](https://bugzil.la/711205)).

12.1

4.2

1.0

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

`binaryType`

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

`bufferedAmount`

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

`close`

4

12

8

4-8

Parameters not supported, see [bug 674716](https://bugzil.la/674716).

10

12.1

5

≤37

18

8

4-8

Parameters not supported, see [bug 674716](https://bugzil.la/674716).

12.1

4.2

1.0

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

`extensions`

Yes

12

8

10

Yes

Yes

Yes

Yes

8

Yes

Yes

Yes

`message_event`

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

`onclose`

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

`open_event`

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

`protocol`

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

`protocol_rfc_6455`

16

12

11

10

15

6

≤37

18

14

14

6

1.0

`readyState`

43

12

19

10

30

10

43

43

19

30

10

4.0

`send`

4

12

18

See [bug 775368](https://bugzil.la/775368).

11-18

Only parameter of type `ArrayBuffer` and `String` supported.

8-11

Only parameter of type `String` supported.

4-8

Only parameter of type `String` supported. Returns `boolean`.

10

12.1

5

≤37

18

18

See [bug 775368](https://bugzil.la/775368).

14-18

Only parameter of type `ArrayBuffer` and `String` supported.

8-14

Only parameter of type `String` supported.

4-8

Only parameter of type `String` supported. Returns `boolean`.

12.1

4.2

1.0

`url`

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

`worker_support`

Yes

≤18

37

?

?

?

Yes

Yes

37

?

?

Yes

See also
--------

-   [RFC 6455 — The WebSocket Protocol](https://datatracker.ietf.org/doc/html/rfc6455)
-   [WebSocket API Specification](https://www.w3.org/TR/websockets/)
-   [Server-Sent Events](server-sent_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API</a>
