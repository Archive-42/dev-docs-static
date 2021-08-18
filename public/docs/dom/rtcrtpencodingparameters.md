RTCRtpEncodingParameters
========================

An instance of the [WebRTC](webrtc_api) API's `RTCRtpEncodingParameters` dictionary describes a single configuration of a [codec](https://developer.mozilla.org/en-US/docs/Glossary/Codec) for an [`RTCRtpSender`](rtcrtpsender). It's used in the [`RTCRtpSendParameters`](rtcrtpsendparameters) describing the configuration of an RTP sender's [`encodings`](rtcrtpsendparameters/encodings); <span class="page-not-created">`RTCRtpDecodingParameters`</span> is used to describe the configuration of an RTP receiver's [`encodings`](rtcrtpreceiveparameters).

Properties
----------

<span class="page-not-created">`active`</span>  
If `true`, the described encoding is currently actively being used. That is, for RTP senders, the encoding is currently being used to send data, while for receivers, the encoding is being used to decode received data. The default value is `true`.

<span class="page-not-created">`codecPayloadType`</span>  
When describing a codec for an [`RTCRtpSender`](rtcrtpsender), `codecPayloadType` is a single 8-bit byte (or octet) specifying the codec to use for sending the stream; the value matches one from the owning [`RTCRtpParameters`](rtcrtpparameters) object's <span class="page-not-created">`codecs`</span> parameter. This value can only be set when creating the transceiver; after that, this value is read only.

<span class="page-not-created">`dtx`</span>  
Only used for an [`RTCRtpSender`](rtcrtpsender) whose [`kind`](mediastreamtrack/kind) is `audio`, this property indicates whether or not to use discontinuous transmission (a feature by which a phone is turned off or the microphone muted automatically in the absence of voice activity). The value is taken from the enumerated string type <span class="page-not-created">`RTCDtxStatus`</span>.

[`maxBitrate`](rtcrtpencodingparameters/maxbitrate)  
An unsigned long integer indicating the maximum number of bits per second to allow for this encoding. Other parameters may further constrain the bit rate, such as the value of `maxFramerate` or transport or physical network limitations.

<span class="page-not-created">`maxFramerate`</span>  
A double-precision floating-point value specifying the maximum number of frames per second to allow for this encoding.

<span class="page-not-created">`ptime`</span>  
An unsigned long integer value indicating the preferred duration of a media packet in milliseconds. This is typically only relevant for audio encodings. The user agent will try to match this as well as it can, but there is no guarantee.

<span class="page-not-created">`rid`</span>  
A [`DOMString`](domstring) which, if set, specifies an **RTP stream ID** (**RID**) to be sent using the RID header extension. This parameter cannot be modified using [`setParameters()`](rtcrtpsender/setparameters). Its value can only be set when the transceiver is first created.

[`scaleResolutionDownBy`](rtcrtpencodingparameters/scaleresolutiondownby)  
Only used for senders whose track's [`kind`](mediastreamtrack/kind) is `video`, this is a double-precision floating-point value specifying a factor by which to scale down the video during encoding. The default value, 1.0, means that the sent video's size will be the same as the original. A value of 2.0 scales the video frames down by a factor of 2 in each dimension, resulting in a video 1/4 the size of the original. The value must not be less than 1.0 (you can't use this to scale the video up).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpencodingparameters">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpEncodingParameters' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCRtpEncodingParameters`

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

`active`

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

`codecPayloadType`

No

No

No

No

?

?

No

No

No

?

?

No

`dtx`

No

No

No

No

?

?

No

No

No

?

?

No

`fec`

No

No

46

This non-standard property should not be used in production code.

No

No

No

No

No

46

This non-standard property should not be used in production code.

No

No

No

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

`maxFramerate`

No

No

No

No

?

?

No

No

No

?

?

No

`priority`

67

The standard version of this property is [`RTCRtpSendParameters.priority`](https://developer.mozilla.org/docs/Web/API/RTCRtpSendParameters/priority).

≤79

The standard version of this property is [`RTCRtpSendParameters.priority`](https://developer.mozilla.org/docs/Web/API/RTCRtpSendParameters/priority).

46

The standard version of this property is [`RTCRtpSendParameters.priority`](https://developer.mozilla.org/docs/Web/API/RTCRtpSendParameters/priority).

No

?

?

67

The standard version of this property is [`RTCRtpSendParameters.priority`](https://developer.mozilla.org/docs/Web/API/RTCRtpSendParameters/priority).

67

The standard version of this property is [`RTCRtpSendParameters.priority`](https://developer.mozilla.org/docs/Web/API/RTCRtpSendParameters/priority).

46

The standard version of this property is [`RTCRtpSendParameters.priority`](https://developer.mozilla.org/docs/Web/API/RTCRtpSendParameters/priority).

?

?

9.0

The standard version of this property is [`RTCRtpSendParameters.priority`](https://developer.mozilla.org/docs/Web/API/RTCRtpSendParameters/priority).

`ptime`

No

No

No

No

?

?

No

No

No

?

?

No

`rid`

No

No

46

The standard version of this property is [`RTCRtpCodecParameters.rid`](https://developer.mozilla.org/docs/Web/API/RTCRtpCodecParameters/rid).

No

No

No

No

No

46

The standard version of this property is [`RTCRtpCodecParameters.rid`](https://developer.mozilla.org/docs/Web/API/RTCRtpCodecParameters/rid).

No

No

No

`rtx`

No

No

46

This non-standard property should not be used in production code.

No

No

No

No

No

46

This non-standard property should not be used in production code.

No

No

No

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

`ssrc`

No

No

46

This non-standard property should not be used in production code.

No

No

No

No

No

46

This non-standard property should not be used in production code.

No

No

No

See also
--------

-   [Introduction to the Real-time Transport Protocol (RTP)](webrtc_api/intro_to_rtp)
-   [`RTCRtpSender`](rtcrtpsender), [`RTCRtpReceiver`](rtcrtpreceiver), and [`RTCRtpTransceiver`](rtcrtptransceiver)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpEncodingParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpEncodingParameters</a>
