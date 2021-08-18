RTCPeerConnection()
===================

The `RTCPeerConnection()` constructor returns a newly-created [`RTCPeerConnection`](../rtcpeerconnection), which represents a connection between the local device and a remote peer.

Syntax
------

    pc = new RTCPeerConnection([configuration]);

### Parameters

 `configuration` <span class="badge inline optional">Optional</span>   
An [`RTCConfiguration` dictionary](#rtcconfiguration_dictionary) providing options to configure the new connection.

### RTCConfiguration dictionary

 [`bundlePolicy`](../rtcconfiguration/bundlepolicy) <span class="badge inline optional">Optional</span>   
Specifies how to handle negotiation of candidates when the remote peer is not compatible with the [SDP BUNDLE standard](https://webrtcstandards.info/sdp-bundle/). This must be one of the values from the enum `RTCBundlePolicy`. If this value isn't included in the dictionary, `"balanced"` is assumed.

 [`certificates`](../rtcconfiguration/certificates) <span class="badge inline optional">Optional</span>   
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of objects of type [`RTCCertificate`](../rtccertificate) which are used by the connection for authentication. If this property isn't specified, a set of certificates is generated automatically for each [`RTCPeerConnection`](../rtcpeerconnection) instance. Although only one certificate is used by a given connection, providing certificates for multiple algorithms may improve the odds of successfully connecting in some circumstances. See [Using certificates](../rtcconfiguration/certificates#using_certificates) for further information.

This configuration option cannot be changed after it is first specified; once the certificates have been set, this property is ignored in future calls to [`RTCPeerConnection.setConfiguration()`](setconfiguration).

 <span class="page-not-created">`iceCandidatePoolSize`</span> <span class="badge inline optional">Optional</span>   
An unsigned 16-bit integer value which specifies the size of the prefetched ICE candidate pool. The default value is 0 (meaning no candidate prefetching will occur). You may find in some cases that connections can be established more quickly by allowing the ICE agent to start fetching ICE candidates before you start trying to connect, so that they're already available for inspection when [`RTCPeerConnection.setLocalDescription()`](setlocaldescription) is called.

Changing the size of the ICE candidate pool may trigger the beginning of ICE gathering.

 [`iceServers`](../rtcconfiguration/iceservers) <span class="badge inline optional">Optional</span>   
An array of [`RTCIceServer`](../rtciceserver) objects, each describing one server which may be used by the ICE agent; these are typically STUN and/or TURN servers. If this isn't specified, the connection attempt will be made with no STUN or TURN server available, which limits the connection to local peers.

 [`iceTransportPolicy`](../rtcconfiguration/icetransportpolicy) <span class="badge inline optional">Optional</span>   
The current ICE transport policy; this must be one of the values from the <span class="page-not-created">`RTCIceTransportPolicy`</span> enumeration. If the policy isn't specified, `all` is assumed by default, allowing all candidates to be considered. A value of `relay` limits the candidates to those relayed through another server, such as a STUN or TURN server.

 <span class="page-not-created">`peerIdentity`</span> <span class="badge inline optional">Optional</span>   
A [`DOMString`](../domstring) which specifies the target peer identity for the [`RTCPeerConnection`](../rtcpeerconnection). If this value is set (it defaults to `null`), the `RTCPeerConnection` will not connect to a remote peer unless it can successfully authenticate with the given name.

 <span class="page-not-created">`rtcpMuxPolicy`</span> <span class="badge inline optional">Optional</span>   
The RTCP mux policy to use when gathering ICE candidates, in order to support non-multiplexed RTCP. The value must be one of those from the [`RTCRtcpMuxPolicy` enum](#rtcrtcpmuxpolicy_enum). The default is `"require"`.

### Return value

A newly-created [`RTCPeerConnection`](../rtcpeerconnection) object, configured as described by `configuration`, if specified; otherwise, configured to appropriate basic defaults.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCPeerConnection`

23

Before Chrome 63 the default value for the `RTCConfiguration.rtcpMuxPolicy` parameter was `"negotiate"`

15

22

No

43

Promise-based version.

37-43

11

≤37

Before Chrome 63 the default value for the `RTCConfiguration.rtcpMuxPolicy` parameter was `"negotiate"`

Yes

Before Chrome 63 the default value for the `RTCConfiguration.rtcpMuxPolicy` parameter was `"negotiate"`

44

43

Promise-based version.

37-43

11

6.0

See also
--------

-   [Signaling and video calling](../webrtc_api/signaling_and_video_calling)
-   [WebRTC architecture overview](../webrtc_api/protocols)
-   [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)
-   [`RTCPeerConnection`](../rtcpeerconnection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/RTCPeerConnection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/RTCPeerConnection</a>
