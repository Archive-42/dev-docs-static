RTCConfiguration.bundlePolicy
=============================

The [`RTCConfiguration`](../rtcconfiguration) dictionary's `bundlePolicy` property is a string value indicating which SDP bundling policy, if any, to use for the underlying [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) streams used by an [`RTCPeerConnection`](../rtcpeerconnection).

The configuration object is used as an input to the [`RTCPeerConnection()`](../rtcpeerconnection/rtcpeerconnection) constructor.

Syntax
------

    let rtcConfiguration = {
      bundlePolicy: policy
    };

    rtcConfiguration.bundlePolicy = policy;

### Value

A [`DOMString`](../domstring) identifying the SDP bundling policy to use for the RTP streams used by the [`RTCPeerConnection`](../rtcpeerconnection). This string, which must be a member of the `RTCBundlePolicy` enumeration, has the following possible values:

`balanced`  
The ICE agent begins by creating one [`RTCDtlsTransport`](../rtcdtlstransport) to handle each type of content added: one for audio, one for video, and one for the RTC data channel, if applicable. If the remote peer isn't BUNDLE-aware, the ICE agent chooses one audio track and one video track and those two tracks are each assigned to the corresponding `RTCDtlsTransport`. All other tracks are ignored by the connection. **This is the default, and most compatible, policy.**

`max-compat`  
The ICE agent intially creates one `RTCDtlsTransport` for each media track and a separate one for the [`RTCDataChannel`](../rtcdatachannel), if one is created. If the remote endpoint can't handle bundling, each media track is negotiated on its own separate transport. This introduces bundling but will fall back to not bundling if the remote peer can't handle it.

`max-bundle`  
The ICE agent starts by creating a single [`RTCDtlsTransport`](../rtcdtlstransport) to handle *all* of the connection's media. If the remote peer isn't bundle-compatible, only one media track is negotiated and the rest are ignored. This maximizes bundling at the risk of losing tracks if the remote peer can't do bundling.

If any other value is specified, no configuration is specified when creating the [`RTCPeerConnection`](../rtcpeerconnection), or if the `bundlePolicy` property isn't included in the [`RTCConfiguration`](../rtcconfiguration) object specified when creating the connection, `balanced` is assumed.

Description
-----------

The `bundlePolicy` configuration option for an [`RTCPeerConnection`](../rtcpeerconnection) specifies how the ICE agent should handle negotiation if the remote peer isn't compatible with the [SDP BUNDLE standard](https://datatracker.ietf.org/doc/html/draft-ietf-mmusic-sdp-bundle-negotiation). If the remote peer *is* bundle compatible, the policy is moot and all media tracks and the data channel are bundled onto a single [`RTCDtlsTransport`](../rtcdtlstransport) at the completion of the negotiation process. Any other transports that were used during negotiation are then closed.

In technical terms, an SDP BUNDLE lets all of the media tracks (identified in the SDP from the `m=` lines) stream between two peers across a single **5-tuple**, that is, from a single IP and port on one peer to a single IP and port on another peer, all using the same [`RTCDtlsTransport`](../rtcdtlstransport).

The goal of bundling is to optimize performance by reducing the overhead of having multiple transports in play. The fewer RTP transports or bundles of RTP streams you have, the better the network performance will be.

All current major browsers are BUNDLE compatible.

Examples
--------

The following example creates a new [`RTCPeerConnection`](../rtcpeerconnection) with a configuration setting the connection's `bundlePolicy` to `max-compat` to maximize compatibility while attempting to optimize network use. It also specifies `stun:stun.example.com` as the [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) server for [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) to use during negotiation.

    let config = {
      iceServers: [
        {
          urls: [ "stun:stun.example.com" ]
        },
      ],
      bundlePolicy: "max-compat"
    };

    let pc = new RTCPeerConnection(config);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcconfiguration-bundlepolicy">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCConfiguration.bundlePolicy' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [WebRTC API](../webrtc_api)
-   [SDP BUNDLE draft specification](https://datatracker.ietf.org/doc/html/draft-ietf-mmusic-sdp-bundle-negotiation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration/bundlePolicy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration/bundlePolicy</a>
