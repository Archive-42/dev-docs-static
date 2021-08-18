RTCPeerConnection.onconnectionstatechange
=========================================

The `RTCPeerConnection.onconnectionstatechange` property specifies an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which is called to handle the `connectionstatechange` event when it occurs on an instance of [`RTCPeerConnection`](../rtcpeerconnection). This happens whenever the aggregate state of the connection changes. The aggregate state is a combination of the states of all of the individual network transports being used by the connection.

Syntax
------

    RTCPeerConnection.onconnectionstatechange = eventHandler;

### Value

A function which is called by the browser when the `connectionstatechange` event occurs on the [`RTCPeerConnection`](../rtcpeerconnection). The function receives as input a single parameter, which is an object of type [`Event`](../event). The event object contains no special information of note; you can look at the value of the peer connection's [`connectionState`](connectionstate) property to determine what the new state is.

Example
-------

    pc.onconnectionstatechange = function(event) {
      switch(pc.connectionState) {
        case "connected":
          // The connection has become fully connected
          break;
        case "disconnected":
        case "failed":
          // One or more transports has terminated unexpectedly or in an error
          break;
        case "closed":
          // The connection has been closed
          break;
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-onconnectionstatechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.onconnectionstatechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onconnectionstatechange`

72

79

No

No

No

11

72

72

No

No

11

11.0

See also
--------

-   The `connectionstatechange` event and its type, [`Event`](../event).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onconnectionstatechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onconnectionstatechange</a>
