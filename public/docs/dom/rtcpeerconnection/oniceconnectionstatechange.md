RTCPeerConnection.oniceconnectionstatechange
============================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCPeerConnection.oniceconnectionstatechange` property is an event handler which specifies a function to be called when the `iceconnectionstatechange` event is fired on an [`RTCPeerConnection`](../rtcpeerconnection) instance. This happens when the state of the connection's ICE agent, as represented by the [`iceConnectionState`](iceconnectionstate) property, changes.

Syntax
------

    RTCPeerConnection.oniceconnectionstatechange = eventHandler;

### Value

This event handler can be set to function which is passed a single input parameter: an [`Event`](../event) object describing the `iceconnectionstatechange` event which occurred. Your code can look at the value of [`RTCPeerConnection.iceConnectionState`](iceconnectionstate) to determine what the new state is.

Example
-------

The example below watches the state of the ICE agent for a failure or unexpected closure and takes appropriate action, such as presenting an error message or attempting to restart the ICE agent.

    pc.oniceconnectionstatechange = function(event) {
      if (pc.iceConnectionState === "failed" ||
          pc.iceConnectionState === "disconnected" ||
          pc.iceConnectionState === "closed") {
        // Handle the failure
      }
    };

Of course, "disconnected" and "closed" don't necessarily indicate errors; these can be the result of normal ICE negotiation, so be sure to handle these properly (if at all).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-oniceconnectionstatechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.oniceconnectionstatechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`oniceconnectionstatechange`

28

15

22

No

43

Promise-based version.

37-43

11

≤37

28

44

43

Promise-based version.

37-43

11

6.0

See also
--------

-   The `iceconnectionstatechange` event and its type, [`Event`](../event).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/oniceconnectionstatechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/oniceconnectionstatechange</a>
