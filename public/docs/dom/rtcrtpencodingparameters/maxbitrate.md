RTCRtpEncodingParameters.maxBitrate
===================================

The [`RTCRtpEncodingParameters`](../rtcrtpencodingparameters) dictionary's `maxBitrate` property specifies the maximum number of bits per second to allow a track encoded with this encoding to use.

Syntax
------

    rtpEncodingParameters.maxBitrate = maxBitsPerSecond;

    rtpEncodingParameters = {
      maxBitrate: maxBitsPerSecond
    };

    maxBitsPerSecond = rtpEncodingParameters.maxBitrate;

### Value

An unsigned long integer value specifying the maximum bandwidth this encoding is permitted to use for a track of media it encodes in terms of bits per second. Other parameters may further reduce the bandwidth used by the track; for example, <span class="page-not-created">`maxFramerate`</span> will, if set low enough, constrain the bandwidth as well.

In addition, there's no guarantee that the network interface can support the specified bandwidth, in which case the actual bandwidth will be lower.

This value is computed using the standard Transport Independent Application Specific Maximum (TIAS) bandwidth as defined by [RFC 3890, section 6.2.2](https://tools.ietf.org/html/rfc3890#section-6.2.2); this is the maximum bandwidth needed without considering protocol overheads from IP, TCP or UDP, and so forth.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpencodingparameters-maxbitrate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpEncodingParameters.maxBitrate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`maxBitrate`

67

≤79

46

No

?

?

67

67

46

?

?

9.0

See also
--------

-   <span class="page-not-created">`RTCRtpEncodingParameters.maxFramerate`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpEncodingParameters/maxBitrate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpEncodingParameters/maxBitrate</a>
