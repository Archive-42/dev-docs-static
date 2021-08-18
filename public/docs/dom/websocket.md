WebSocket
=========

The `WebSocket` object provides the API for creating and managing a [WebSocket](websockets_api) connection to a server, as well as for sending and receiving data on the connection.

To construct a `WebSocket`, use the `WebSocket()` constructor.

**Note:** This feature is available in [Web Workers](web_workers_api).

Constructor
-----------

[`WebSocket(url[, protocols])`](websocket/websocket)  
Returns a newly created `WebSocket` object.

Constants
---------

<table><thead><tr class="header"><th>Constant</th><th>Value</th></tr></thead><tbody><tr class="odd"><td><code>WebSocket.CONNECTING</code></td><td><code>0</code></td></tr><tr class="even"><td><code>WebSocket.OPEN</code></td><td><code>1</code></td></tr><tr class="odd"><td><code>WebSocket.CLOSING</code></td><td><code>2</code></td></tr><tr class="even"><td><code>WebSocket.CLOSED</code></td><td><code>3</code></td></tr></tbody></table>

Properties
----------

[`WebSocket.binaryType`](websocket/binarytype)  
The binary data type used by the connection.

 [`WebSocket.bufferedAmount`](websocket/bufferedamount) <span class="badge inline readonly">Read only </span>   
The number of bytes of queued data.

 [`WebSocket.extensions`](websocket/extensions) <span class="badge inline readonly">Read only </span>   
The extensions selected by the server.

[`WebSocket.onclose`](websocket/onclose)  
An event listener to be called when the connection is closed.

[`WebSocket.onerror`](websocket/onerror)  
An event listener to be called when an error occurs.

[`WebSocket.onmessage`](websocket/onmessage)  
An event listener to be called when a message is received from the server.

[`WebSocket.onopen`](websocket/onopen)  
An event listener to be called when the connection is opened.

 [`WebSocket.protocol`](websocket/protocol) <span class="badge inline readonly">Read only </span>   
The sub-protocol selected by the server.

 [`WebSocket.readyState`](websocket/readystate) <span class="badge inline readonly">Read only </span>   
The current state of the connection.

 [`WebSocket.url`](websocket/url) <span class="badge inline readonly">Read only </span>   
The absolute URL of the WebSocket.

Methods
-------

[`WebSocket.close([code[, reason]])`](websocket/close)  
Closes the connection.

[`WebSocket.send(data)`](websocket/send)  
Enqueues data to be transmitted.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`close`](websocket/close_event)  
Fired when a connection with a `WebSocket` is closed.  
Also available via the [`onclose`](websocket/onclose) property

[`error`](websocket/error_event)  
Fired when a connection with a `WebSocket` has been closed because of an error, such as when some data couldn't be sent.  
Also available via the [`onerror`](websocket/onerror) property.

[`message`](websocket/message_event)  
Fired when data is received through a `WebSocket`.  
Also available via the [`onmessage`](websocket/onmessage) property.

[`open`](websocket/open_event)  
Fired when a connection with a `WebSocket` is opened.  
Also available via the [`onopen`](websocket/onopen) property.

Examples
--------

    // Create WebSocket connection.
    const socket = new WebSocket('ws://localhost:8080');

    // Connection opened
    socket.addEventListener('open', function (event) {
        socket.send('Hello Server!');
    });

    // Listen for messages
    socket.addEventListener('message', function (event) {
        console.log('Message from server ', event.data);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#network">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

-   [Writing WebSocket client applications](websockets_api/writing_websocket_client_applications)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket</a>
