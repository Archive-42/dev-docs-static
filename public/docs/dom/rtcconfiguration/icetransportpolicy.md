RTCConfiguration.iceTransportPolicy
===================================

The [WebRTC Device API](../webrtc_api) dictionary [`RTCConfiguration`](../rtcconfiguration)'s `iceTransportPolicy` property is a string indicating the transport selection policy the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) agent should use during negotiation of connections. Its value must come from the <span class="page-not-created">`RTCIceTransportPolicy`</span> enumerated type.

If this property isn't included in the `RTCConfiguration`, the default value, `all`, is used.

Syntax
------

    let rtcConfiguration = {
      iceTransportPolicy: policy
    };

    rtcConfiguration.iceTransportPolicy = policy;
    let policy = rtcConfiguration.iceTransportPolicy;

### Value

A [`DOMString`](../domstring) which indicates what [ICE candidate policy](https://rtcweb-wg.github.io/jsep/#rfc.section.3.5.3) the ICE agent should use during the negotiation process, per the [JSEP standard](https://rtcweb-wg.github.io/jsep/). The permitted values are:

`all`  
The ICE agent is permitted to use any kind of candidate, including both local and relay candidates. The agent—or the browser itself—may still perform some form of IP filtering on the incoming candidates for reasons including privacy and security, as well as to limit the number of candidates. **This is the default.**

`relay`  
The ICE agent only considers media relay candidates when evaluating candidates. This includes, for example, those candidates relayed by a [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) or [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server.

This can be used to prevent the remote endpoint from receiving the user's IP addresses, which may be important in some security situations. For example, in a video calling application, the app may want to prevent unknown callers from learning the callee's IP addresses until the callee has agreed to receive the call.

Examples
--------

In this example, a new connection is configured to only accept relay candidates.

    let config = {
      iceServers: [
        {
          urls: [ "stun:stun.example.com" ]
        },
      ],
      iceTransportPolicy: "relay"
    };

    let pc = new RTCPeerConnection(config);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcconfiguration-icetransportpolicy">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCCandidate.iceTransportPolicy' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration/iceTransportPolicy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration/iceTransportPolicy</a>
