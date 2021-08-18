# RTCIceCredentialType

The WebRTC API's `RTCIceCredentialType` enumerated string type defines the authentication method used to gain access to an [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) server identified by an [`RTCIceServer`](rtciceserver) object.

## Values

`oauth`  
The [`RTCIceServer`](rtciceserver) requires the use of OAuth 2.0 to authenticate in order to use the ICE server described. This process is detailed in [RFC 7635](https://tools.ietf.org/html/rfc7635). This property was formerly called `token`.

`password`  
The `RTCIceServer` requires a username and password to authenticate prior to using the described ICE server.

## Obsolete values

The following values are no longer part of the WebRTC specification, but were in the past.

`token`  
Authenticating with the ICE server requires the use of an OAuth 2.0 token as defined in [RFC 7635](https://tools.ietf.org/html/rfc7635). This value has been renamed to `oauth`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecredentialtype">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCredentialType' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`RTCIceCredentialType`

No

No

47

No

No

?

No

No

47

No

?

No

`oauth`

No

No

No

No

No

?

No

No

No

No

?

No

`password`

No

No

47

No

No

?

No

No

47

No

?

No

`token`

No

No

47-68

No

No

?

No

No

47-68

No

?

No

## See also

- [`RTCIceServer`](rtciceserver)
- [`RTCIceServer.credential`](rtciceserver/credential)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCredentialType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCredentialType</a>
