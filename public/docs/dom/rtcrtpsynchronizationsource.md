RTCRtpSynchronizationSource
===========================

The `RTCRtpSynchronizationSource` dictionary of the [WebRTC API](webrtc_api) is used by [`getSynchronizationSources()`](rtcrtpreceiver/getsynchronizationsources) to describe a particular synchronization source (SSRC). A synchronization source is a single source that shares timing and sequence number space. Since `RTCRtpSynchronizationSource` implements [`RTCRtpContributingSource`](rtcrtpcontributingsource), its properties are also available.

The information provided is based on the last ten seconds of media received.

While the published specification describes this as an interface, it has since been changed to a dictionary in follow-up drafts.

Properties
----------

*Also implements the properties of [`RTCRtpContributingSource`](rtcrtpcontributingsource).*

 [`voiceActivityFlag`](rtcrtpsynchronizationsource/voiceactivityflag) <span class="badge inline optional">Optional</span>   
A Boolean value indicating whether or not voice activity is included in the last RTP packet played from the source. If the peer has indicated that it's not supporting voice activity detection, this field is not provided.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpsynchronizationsource">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpSynchronizationSource' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCRtpSynchronizationSource`

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

`voiceActivityFlag`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSynchronizationSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSynchronizationSource</a>
