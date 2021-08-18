# RTCIceCandidateInit.candidate

The optional property `candidate` in the **[`RTCIceCandidateInit`](../rtcicecandidateinit)** dictionary specifies the value of the [`RTCIceCandidate`](../rtcicecandidate) object's [`candidate`](../rtcicecandidate/candidate) property.

## Value

A [`DOMString`](../domstring) describing the properties of the candidate, taken directly from the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) attribute `"candidate"`. The candidate string specifies the network connectivity information for the candidate. If the `candidate` is an empty string (`""`), the end of the candidate list has been reached; this candidate is known as the "end-of-candidates" marker.

The syntax of the candidate string is described in [RFC 5245, section 15.1](https://tools.ietf.org/html/rfc5245#section-15.1). For an a-line (attribute line) that looks like this:

    a=candidate:4234997325 1 udp 2043278322 192.168.0.56 44323 typ host

the corresponding `candidate` string's value will be `"candidate:4234997325 1 udp 2043278322 192.168.0.56 44323 typ host"`.

The [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) always prefers candidates with the highest [`priority`](../rtcicecandidate/priority), all else being equal. In the example above, the priority is `2043278322`. The attributes are all separated by a single space character, and are in a specific order. The complete list of attributes for this example candidate is:

- [`foundation`](../rtcicecandidate/foundation) = 4234997325
- [`component`](../rtcicecandidate/component) = `"rtp"` (the number 1 is encoded to this string; 2 becomes `"rtcp"`)
- [`protocol`](../rtcicecandidate/protocol) = `"udp"`
- [`priority`](../rtcicecandidate/priority) = 2043278322
- [`ip`](../rtcicecandidate/address) = `"192.168.0.56"`
- [`port`](../rtcicecandidate/port) = 44323
- [`type`](../rtcicecandidate/type) = `"host"`

## Example

When a new ICE candidate is received by your signaling code from the remote peer, you need to construct the `RTCIceCandidate` object that encapsulates it. This is done in the event handler for the `icecandidate` event. If your client-side signaling layer builds and transmits a JSON string including the candidate to the remote peer, the remote peer might handle receiving that JSON message like this:

    function gotICECandidateMessage(msg) {
      var iceCandidate = new RTCIceCandidate({
            candidate: msg.candidate;
      });

      pc.addIceCandidate(iceCandidate).catch({
        /* handle error */
      });
    }

It's helpful to note that for backward compatibility with older versions of the WebRTC specification, the [`RTCIceCandidate()`](../rtcicecandidate/rtcicecandidate) constructor accepts the value of `candidate` as its only input, in place of the `RTCIceCandidateInit` dictionary. That usage would change the above sample to look like this:

    function gotICECandidateMessage(msg) {
      var iceCandidate = new RTCIceCandidate(msg.candidate);

      pc.addIceCandidate(iceCandidate).catch({
        /* handle error */
      });
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidateinit-candidate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidateInit.candidate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

## Browser compatibility

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

`candidate`

Yes

≤18

22

Prior to Firefox 68, the `candidate` property was required; Firefox 68 and later make it optional per a mid-2017 specification update.

No

Yes

?

Yes

Yes

Yes

Prior to Firefox 68, the `candidate` property was required; Firefox 68 and later make it optional per a mid-2017 specification update.

Yes

?

Yes

## See also

- [WebRTC API](../webrtc_api)
- [`RTCIceCandidate.candidate`](../rtcicecandidate/candidate)
- [`RTCPeerConnection.addIceCandidate()`](../rtcpeerconnection/addicecandidate)
- `icecandidate`
- [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateInit/candidate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateInit/candidate</a>
