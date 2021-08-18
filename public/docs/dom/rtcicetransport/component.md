# RTCIceTransport.component

The read-only **[`RTCIceTransport`](../rtcicetransport)** property `component` specifies whether the object is serving to transport RTP or RTCP. The value is one of the strings in [`RTCIceComponent`](../rtcicecomponent).

## Syntax

    iceComponent = RTCIceTransport.component;

### Value

A [`DOMString`](../domstring) whose value comes from the enumerated type [`RTCIceComponent`](../rtcicecomponent):

`"rtp"`  
Identifies an ICE transport which is being used for the [Real-time Transport Protocol](../webrtc_api/intro_to_rtp) (RTP), or for RTP multiplexed with the RTP Control Protocol (RTCP). RTP is defined in [RFC 3550](https://tools.ietf.org/html/rfc3550). An `RTCIceComponent` of this value corresponds to the component ID field in the `candidate` a-line with the value 1.

`"rtcp"`  
Identifies an ICE transport being used for RTCP, which is defined in [RFC 3550, section 6](https://tools.ietf.org/html/rfc3550#section-6). This value of `RTCIceComponent` corresponds to the component ID 2.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-icetransport-component">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTransport.component' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`component`

No

13-79

No

No

No

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/component" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/component</a>
