RTCPeerConnection.setConfiguration()
====================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCPeerConnection.setConfiguration()` method sets the current configuration of the [`RTCPeerConnection`](../rtcpeerconnection) based on the values included in the specified [`RTCConfiguration`](../rtcconfiguration) object. This lets you change the ICE servers used by the connection and which transport policies to use.

The most common use case for this method (and even then, probably not a very common use case) is to replace the set of ICE servers to be used. Two potential scenarios in which this might be done:

-   The [`RTCPeerConnection`](../rtcpeerconnection) was instantiated without specifying any ICE servers. If, for example, the [`RTCPeerConnection()`](rtcpeerconnection) constructor was called with no parameters, you would have to then call `setConfiguration()` to add ICE servers before ICE negotiation could begin.
-   Renegotiation of the connection is needed, and a different set of ICE servers needs to be used for some reason. Perhaps the user has moved into a new region, so using new regional ICE servers is necessary, for example. In this situation, one might call `setConfiguration()` to switch to new regional ICE servers, then initiate an [ICE restart](../webrtc_api/session_lifetime#ice_restart).

You cannot change the identity information for a connection once it's already been set.

Syntax
------

    RTCPeerConnection.setConfiguration(configuration);

### Parameters

`configuration`  
An [`RTCConfiguration`](../rtcconfiguration) object which provides the options to be set. The changes are not additive; instead, the new values completely replace the existing ones.

### Exceptions

`InvalidAccessError`  
One or more of the URLs specified in `configuration.iceServers` is a [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server, but complete login information is not provided (that is, either the [`RTCIceServer.username`](../rtciceserver/username) or <span class="page-not-created">`RTCIceServer.credentials`</span> is missing). This prevents successful login to the server.

`InvalidModificationError`  
The `configuration` includes changed identity information, but the connection already has identity information specified. This happens if `configuration.peerIdentity` or `configuration.certificates` is set and their values differ from the current configuration.

`InvalidStateError`  
The [`RTCPeerConnection`](../rtcpeerconnection) is closed.

`SyntaxError`  
One or more of the URLs provided in the `configuration.iceServers` list is invalid.

Example
-------

In this example, it has already been determined that ICE restart is needed, and that negotiation needs to be done using a different ICE server.

    var restartConfig = { iceServers: [{
                              urls: "turn:asia.myturnserver.net",
                              username: "allie@oopcode.com",
                              credential: "topsecretpassword"
                          }]
    };

    myPeerConnection.setConfiguration(restartConfig);

    myPeerConnection.createOffer({"iceRestart": true}).then(function(offer) {
      return myPeerConnection.setLocalDescription(offer);
    })
    .then(function() {
      // send the offer to the other peer using the signaling server
    })
    .catch(reportError);

First, a new [`RTCConfiguration`](../rtcconfiguration) is created, `restartConfig`, specifying the new ICE server and its credentials. This is then passed into `setConfiguration()`. ICE negotiation is restarted by calling [`createOffer()`](createoffer), specifying `true` as the value of the `iceRestart` option. From there, we handle the process as usual, by setting the local description to the returned offer and then sending that offer to the other peer.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-setconfiguration">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'setConfiguration()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`setConfiguration`

48

79

No

See [bug 1253706](https://bugzil.la/1253706).

No

43

Promise-based version.

37-43

11

48

48

No

See [bug 1253706](https://bugzil.la/1253706).

43

Promise-based version.

37-43

11

6.0

See also
--------

-   [`RTCPeerConnection.getConfiguration()`](getconfiguration)
-   [`RTCConfiguration`](../rtcconfiguration)
-   [`RTCPeerConnection`](../rtcpeerconnection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setConfiguration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setConfiguration</a>
