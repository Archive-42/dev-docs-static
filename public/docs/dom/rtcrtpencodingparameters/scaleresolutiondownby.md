RTCRtpEncodingParameters.scaleResolutionDownBy
==============================================

The [`RTCRtpEncodingParameters`](../rtcrtpencodingparameters) dictionary's `scaleResolutionDownBy` property can be used to specify a factor by which to reduce the size of a video track during encoding.

This property is only available for tracks whose [`kind`](../mediastreamtrack/kind) is `video`.

Syntax
------

    rtpEncodingParameters.scaleResolutionDownBy = scalingFactor;

    rtpEncodingParameters = {
      scaleResolutionDownBy: scalingFactor
    };

### Value

A double-precison floating-point number specifying the amount by which to reduce the size of the video during encoding. The default value, 1.0, means that the video will be encoded at its original size. A value of 2.0 would reduce the size of the video by a factor of 2 both horizontally and vertically, resulting in a video 25% the original size.

A value less than 1.0 would cause the video to get larger rather than smaller, which is not the intent of this property. Therefore, specifying a value less than 1.0 is not permitted and will cause a `RangeError` exception to be thrown by [`RTCPeerConnection.addTransceiver()`](../rtcpeerconnection/addtransceiver) or [`RTCRtpSender.setParameters()`](../rtcrtpsender/setparameters).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpencodingparameters-scaleresolutiondownby">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpEncodingParameters.scaleResolutionDownBy' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`scaleResolutionDownBy`

74

No

46

No

?

?

74

74

46

?

?

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpEncodingParameters/scaleResolutionDownBy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpEncodingParameters/scaleResolutionDownBy</a>
