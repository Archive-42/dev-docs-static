RTCSessionDescription.sdp
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The property `RTCSessionDescription.sdp` is a read-only [`DOMString`](../domstring) containing the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) which describes the session.

Syntax
------

    var value = sessionDescription.sdp;
    sessionDescription.sdp = value;

### Value

The value is a [`DOMString`](../domstring) containing an SDP message like this one:

     v=0
     o=alice 2890844526 2890844526 IN IP4 host.anywhere.com
     s=
     c=IN IP4 host.anywhere.com
     t=0 0
     m=audio 49170 RTP/AVP 0
     a=rtpmap:0 PCMU/8000
     m=video 51372 RTP/AVP 31
     a=rtpmap:31 H261/90000
     m=video 53000 RTP/AVP 32
     a=rtpmap:32 MPV/90000

Example
-------

    // The remote description has been set previously on pc, an RTCPeerConnection

    alert(pc.remoteDescription.sdp);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcsessiondescription-sdp">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCSessionDescription.sdp' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`sdp`

Yes

15

Yes

No

Yes

11

Yes

Yes

Yes

Yes

11

Yes

See also
--------

-   [WebRTC](../webrtc_api)
-   The standard for using SDP in an offer/answer protocol [RFC 3264](https://tools.ietf.org/html/rfc3264).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/sdp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/sdp</a>
