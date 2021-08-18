RTCPeerConnectionIceErrorEvent.address
======================================

The [`RTCPeerConnectionIceErrorEvent`](../rtcpeerconnectioniceerrorevent) property `address` is a string which indicates the local IP address being used to communicate with the [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) or [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server during negotiations. The error which occurred involved this address.

Syntax
------

    let address = rtcPeerConnectionIceErrorEvent.address;

### Value

A [`DOMString`](../domstring) which specifies the local IP address of the network connection to the ICE server with which negotiations were occurring when the error occurred. This address identifies the network interface on the local device which is being used to attempt to establish the connection to the remote peer.

This can be useful on multi-homed systems—devices with more than one network connection—to determine which network interface is being used. For example, on a mobile phone, there are typically at least two network interfaces available: the cellular connection and a WiFi connection.

If the local IP address isn't exposed as part of a local candidate, the value of `address` is `null`.

Examples
--------

This example creates a handler for [`icecandidateerror`](../rtcpeerconnection/icecandidateerror_event) events which creates human readable messages describing the local network interface for the connection as well as the ICE server that was being used to try to open the connection, then calls a function to display those as well as the event's <span class="page-not-created">`errorText`</span> property's contents.

    pc.addEventListener("icecandidateerror", (event) => {
      let networkInfo = `[Local interface: ${event.address}:${event.port}`;
      let iceServerInfo = `[ICE server: ${event.url}`;

      showMessage(errorText, iceServerInfo, networkInfo);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnectioniceerrorevent-address">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnectionIceErrorEvent.address' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCPeerConnectionIceErrorEvent.address`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceErrorEvent/address" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceErrorEvent/address</a>
