RTCRtpCodecCapability
=====================

The [WebRTC API's](webrtc_api) `RTCRtpCodecCapability` dictionary provides information describing the capabilities of a single [media codec](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/WebRTC_codecs).

Properties
----------

 <span class="page-not-created">`channels`</span> <span class="badge inline optional">Optional</span>   
An unsigned integer value indicating the maximum number of channels supported by the codec; for example, a codec that supports only mono sound would have a value of 1; stereo codecs would have a 2, etc.

<span class="page-not-created">`clockRate`</span>  
An unsigned long integer specifying the codec's clock rate in Hertz (Hz). The IANA maintains a [list of codecs and their parameters](https://www.iana.org/assignments/rtp-parameters/rtp-parameters.xhtml#rtp-parameters-1), including their clock rates.

<span class="page-not-created">`mimeType`</span>  
A [`DOMString`](domstring) indicating the codec's MIME media type and subtype. See [Codecs used by WebRTC](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/WebRTC_codecs) for details about potential codecs that might be referenced here.

 <span class="page-not-created">`sdpFmtpLine`</span> <span class="badge inline optional">Optional</span>   
A [`DOMString`](domstring) giving the format specific parameters field from the `a=fmtp` line in the SDP which corresponds to the codec, if such a line exists. If there is no parameters field, this property is left out.

Description
-----------

`RTCRtpCodecCapabilities` describes the basic parameters for a single codec supported by the user's device. An array of objects of this type is returned in the <span class="page-not-created">`codecs`</span> property of the [`RTCRtpCapabilities`](rtcrtpcapabilities) object returned in response to a call to either of the static functions [`RTCRtpSender.getCapabilities()`](rtcrtpsender/getcapabilities) or [`RTCRtpReceiver.getCapabilities()`](rtcrtpreceiver/getcapabilities).

Examples
--------

TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcrtpcodeccapability">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpCodecCapability' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCRtpCodecCapability`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpCodecCapability" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpCodecCapability</a>
