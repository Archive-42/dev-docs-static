RTCConfiguration
================

The `RTCConfiguration` dictionary is used to provide configuration options for an [`RTCPeerConnection`](rtcpeerconnection). It may be passed into the constructor when instantiating a connection, or used with the [`RTCPeerConnection.getConfiguration()`](rtcpeerconnection/getconfiguration) and [`RTCPeerConnection.setConfiguration()`](rtcpeerconnection/setconfiguration) methods, which allow inspecting and changing the configuration while a connection is established.

The options include ICE server and transport settings and identity information.

Properties
----------

 [`bundlePolicy`](rtcconfiguration/bundlepolicy) <span class="badge inline optional">Optional</span>   
Specifies how to handle negotiation of candidates when the remote peer is not compatible with the [SDP BUNDLE standard](https://webrtcstandards.info/sdp-bundle/). This must be one of the values from the enum `RTCBundlePolicy`. If this value isn't included in the dictionary, `"balanced"` is assumed.

 [`certificates`](rtcconfiguration/certificates) <span class="badge inline optional">Optional</span>   
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of objects of type [`RTCCertificate`](rtccertificate) which are used by the connection for authentication. If this property isn't specified, a set of certificates is generated automatically for each [`RTCPeerConnection`](rtcpeerconnection) instance. Although only one certificate is used by a given connection, providing certificates for multiple algorithms may improve the odds of successfully connecting in some circumstances. See [Using certificates](rtcconfiguration/certificates#using_certificates) for further information.

This configuration option cannot be changed after it is first specified; once the certificates have been set, this property is ignored in future calls to [`RTCPeerConnection.setConfiguration()`](rtcpeerconnection/setconfiguration).

 <span class="page-not-created">`iceCandidatePoolSize`</span> <span class="badge inline optional">Optional</span>   
An unsigned 16-bit integer value which specifies the size of the prefetched ICE candidate pool. The default value is 0 (meaning no candidate prefetching will occur). You may find in some cases that connections can be established more quickly by allowing the ICE agent to start fetching ICE candidates before you start trying to connect, so that they're already available for inspection when [`RTCPeerConnection.setLocalDescription()`](rtcpeerconnection/setlocaldescription) is called.

Changing the size of the ICE candidate pool may trigger the beginning of ICE gathering.

 [`iceServers`](rtcconfiguration/iceservers) <span class="badge inline optional">Optional</span>   
An array of [`RTCIceServer`](rtciceserver) objects, each describing one server which may be used by the ICE agent; these are typically STUN and/or TURN servers. If this isn't specified, the connection attempt will be made with no STUN or TURN server available, which limits the connection to local peers.

 [`iceTransportPolicy`](rtcconfiguration/icetransportpolicy) <span class="badge inline optional">Optional</span>   
The current ICE transport policy; this must be one of the values from the <span class="page-not-created">`RTCIceTransportPolicy`</span> enumeration. If the policy isn't specified, `all` is assumed by default, allowing all candidates to be considered. A value of `relay` limits the candidates to those relayed through another server, such as a STUN or TURN server.

 <span class="page-not-created">`peerIdentity`</span> <span class="badge inline optional">Optional</span>   
A [`DOMString`](domstring) which specifies the target peer identity for the [`RTCPeerConnection`](rtcpeerconnection). If this value is set (it defaults to `null`), the `RTCPeerConnection` will not connect to a remote peer unless it can successfully authenticate with the given name.

 <span class="page-not-created">`rtcpMuxPolicy`</span> <span class="badge inline optional">Optional</span>   
The RTCP mux policy to use when gathering ICE candidates, in order to support non-multiplexed RTCP. The value must be one of those from the [`RTCRtcpMuxPolicy` enum](#rtcrtcpmuxpolicy_enum). The default is `"require"`.

Constants
---------

### RTCBundlePolicy enum

The `RTCBundlePolicy` enum defines string constants which are used to request a specific policy for gathering ICE candidates if the remote peer isn't "BUNDLE-aware" (compatible with the [SDP BUNDLE standard](https://webrtcstandards.info/sdp-bundle/) for bundling multiple media streams on a single transport link). All browser implementations are BUNDLE-aware.

If the remote endpoint is BUNDLE-aware, all media tracks and data channels are bundled onto a single transport at the completion of negotiation, regardless of policy used, and any superfluous transports that were created initially are closed at that point.

**Note:** In technical terms, a BUNDLE lets all media flow between two peers flow across a single **5-tuple**; that is, from a single IP and port on one peer to a single IP and port on the other peer, using the same transport protocol.

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>"balanced"</code></td><td>The ICE agent initially creates one <a href="rtcdtlstransport"><code>RTCDtlsTransport</code></a> for each type of content added: audio, video, and data channels. If the remote endpoint is not BUNDLE-aware, then each of these DTLS transports then handles all the communication for one type of data.</td></tr><tr class="even"><td><code>"max-compat"</code></td><td>The ICE agent initially creates one <a href="rtcdtlstransport"><code>RTCDtlsTransport</code></a> per media track and a separate one for data channels. If the remote endpoint is not BUNDLE-aware, everything is negotiated on these separate DTLS transports.</td></tr><tr class="odd"><td><code>"max-bundle"</code></td><td>The ICE agent initially creates only a single <a href="rtcdtlstransport"><code>RTCDtlsTransport</code></a> to carry all of the <code>RTCPeerConnection</code>'s data. If the remote endpoint is not BUNDLE-aware, then only a single track will be negotiated and the rest ignored.</td></tr></tbody></table>

### RTCIceTransportPolicy enum

The `RTCIceTransportPolicy` enum defines string constants which can be used to limit the transport policies of the ICE candidates to be considered during the connection process.

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>"all"</code></td><td>All ICE candidates will be considered.</td></tr><tr class="even"><td><code>"public" </code><span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Only ICE candidates with public IP addresses will be considered. <em>Removed from the specification's May 13, 2016 working draft.</em></td></tr><tr class="odd"><td><code>"relay"</code></td><td>Only ICE candidates whose IP addresses are being relayed, such as those being passed through a TURN server, will be considered.</td></tr></tbody></table>

### RTCRtcpMuxPolicy enum

The `RTCRtcpMuxPolicy` enum defines string constants which specify what ICE candidates are gathered to support non-multiplexed RTCP. **&lt;&lt;&lt;add a link to info about multiplexed RTCP.**

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>"negotiate"</code></td><td>Instructs the ICE agent to gather both <a href="https://developer.mozilla.org/en-US/docs/Glossary/RTP">RTP</a> and <a href="https://developer.mozilla.org/en-US/docs/Glossary/RTCP">RTCP</a> candidates. If the remote peer can multiplex RTCP, then RTCP candidates are multiplexed atop the corresponding RTP candidates. Otherwise, both the RTP and RTCP candidates are returned, separately.</td></tr><tr class="even"><td><code>"require"</code></td><td>Tells the ICE agent to gather ICE candidates for only RTP, and to multiplex RTCP atop them. If the remote peer doesn't support RTCP multiplexing, then session negotiation fails.</td></tr></tbody></table>

Example
-------

The configuration below establishes two ICE servers. The first one, `stun:stun.services.mozilla.com`, requires authentication, so the username and password are provided. The second server has two URLs: `stun:stun.example.com` and `stun:stun-1.example.com`.

    var configuration = { iceServers: [{
                              urls: "stun:stun.services.mozilla.com",
                              username: "louis@mozilla.com",
                              credential: "webrtcdemo"
                          }, {
                              urls: ["stun:stun.example.com", "stun:stun-1.example.com"]
                          }]
    };

    var pc = new RTCPeerConnection(configuration);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcconfiguration">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCConfiguration' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCConfiguration`

23

≤79

?

No

Yes

?

≤37

57

?

Yes

?

7.0

`bundlePolicy`

23

≤79

?

No

Yes

?

≤37

57

?

Yes

?

7.0

`certificates`

23

≤79

?

No

Yes

?

≤37

57

?

Yes

?

7.0

`iceCandidatePoolSize`

23

≤79

?

No

Yes

?

≤37

57

?

Yes

?

7.0

`iceServers`

23

≤79

?

No

Yes

?

≤37

57

?

Yes

?

7.0

`iceTransportPolicy`

23

≤79

?

No

Yes

?

≤37

57

?

Yes

?

7.0

`peerIdentity`

23

≤79

?

No

Yes

?

≤37

57

?

Yes

?

7.0

`rtcpMuxPolicy`

57

Default for `rtcpMuxPolicy` is `require`

≤79

Default for `rtcpMuxPolicy` is `require`

?

No

44

Default for `rtcpMuxPolicy` is `require`

?

57

57

?

Yes

?

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration</a>
