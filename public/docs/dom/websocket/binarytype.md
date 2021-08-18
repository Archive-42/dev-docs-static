WebSocket.binaryType
====================

The `WebSocket.binaryType` property controls the type of binary data being received over the WebSocket connection.

Syntax
------

    var binaryType = aWebSocket.binaryType;

Value
-----

A [`DOMString`](../domstring):

`"blob"`  
Use [`Blob`](../blob) objects for binary data. This is the default value.

`"arraybuffer"`  
Use [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) objects for binary data.

Examples
--------

    // Create WebSocket connection.
    const socket = new WebSocket("ws://localhost:8080");
    // Change binary type from "blob" to "arraybuffer"
    socket.binaryType = "arraybuffer";

    // Listen for messages
    socket.addEventListener("message", function (event) {
        if(event.data instanceof ArrayBuffer) {
            // binary frame
            const view = new DataView(event.data);
            console.log(view.getInt32(0));
        } else {
            // text frame
            console.log(event.data);
        }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-websocket-binarytype">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket: binaryType' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/binaryType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/binaryType</a>
