# RTCIceCandidateInit.usernameFragment

The optional property `usernameFragment` in the **[`RTCIceCandidateInit`](../rtcicecandidateinit)** dictionary specifies the value of the [`RTCIceCandidate`](../rtcicecandidate) object's [`usernameFragment`](../rtcicecandidate/usernamefragment) property.

## Value

A [`DOMString`](../domstring) containing the username fragment (usually referred to in shorthand as "ufrag" or "ice-ufrag") that, along with the ICE password ("ice-pwd"), uniquely identifies a single ongoing ICE interaction, including for any communication with the [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) server. The string may be up to 256 characters long, and has no default value.

#### Randomization

At least 24 bits of the text in the `ufrag` are required to be randomly selected by the ICE layer at the beginning of the ICE session. The specifics for which bits are random and what the remainder of the `ufrag` text are left up to the browser implementation to decide. For example, a browser might choose to always use a 24-character `ufrag` in which bit 4 of each character is randomly selected between 0 and 1. Another example: it might take a user-defined string and append three 8-bit random bytes to the end. Or perhaps every character is entirely random.

## Example

...

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidateinit-usernamefragment">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidateInit.usernameFragment' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`usernameFragment`

Yes

≤18

67

No

Yes

?

Yes

Yes

67

Yes

?

Yes

## See also

- [WebRTC API](../webrtc_api)
- [`RTCIceCandidate.usernameFragment`](../rtcicecandidate/usernamefragment)
- [`RTCPeerConnection.addIceCandidate()`](../rtcpeerconnection/addicecandidate)
- `icecandidate`
- [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateInit/usernameFragment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateInit/usernameFragment</a>
