RTCRtpContributingSource
========================

The `RTCRtpContributingSource` dictionary of the [WebRTC API](webrtc_api) is used by [`getContributingSources()`](rtcrtpreceiver/getcontributingsources) to provide information about a given contributing source (CSRC), including the most recent time a packet that the source contributed was played out.

The information provided is based on the last ten seconds of media received.

Properties
----------

 [`audioLevel`](rtcrtpcontributingsource/audiolevel) <span class="badge inline optional">Optional</span>   
A double-precision floating-point value between 0 and 1 specifying the audio level contained in the last RTP packet played from this source.

 [`rtpTimestamp`](rtcrtpcontributingsource/rtptimestamp) <span class="badge inline optional">Optional</span>   
The RTP timestamp of the media played out at the time indicated by `timestamp`. This value is a source-generated time value which can be used to help with sequencing and synchronization.

 [`source`](rtcrtpcontributingsource/source) <span class="badge inline optional">Optional</span>   
A 32-bit unsigned integer value specifying the CSRC identifier of the contributing source.

 [`timestamp`](rtcrtpcontributingsource/timestamp) <span class="badge inline optional">Optional</span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) indicating the most recent time at which a frame originating from this source was delivered to the receiver's [`MediaStreamTrack`](mediastreamtrack)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpcontributingsource">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpContributingSource' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCRtpContributingSource`

59

≤79

59

No

No

?

59

59

59

No

?

7.0

`audioLevel`

No

No

59

No

No

?

No

No

59

No

?

No

`source`

59

≤79

59

No

No

?

59

59

59

No

?

7.0

`timestamp`

59

≤79

59

Starting in version 60, the `timestamp` is correctly computed based on the window's `Performance` time, rather than `Date.getTime()`.

No

No

?

59

59

59

Starting in version 60, the `timestamp` is correctly computed based on the window's `Performance` time, rather than `Date.getTime()`.

No

?

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpContributingSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpContributingSource</a>
