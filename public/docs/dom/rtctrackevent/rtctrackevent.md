RTCTrackEvent()
===============

The `RTCTrackEvent()` constructor creates and returns a new [`RTCTrackEvent`](../rtctrackevent) object, configured to describe the track which has been added to the [`RTCPeerConnection`](../rtcpeerconnection).

In general, you won't need to use this constructor, as `RTCTrackEvent` objects are created by WebRTC and delivered to your `RTCPeerConnector`'s [`ontrack`](../rtcpeerconnection/ontrack) event handler as appropriate.

Syntax
------

    trackEvent = new RTCTrackEvent(eventInfo);

### Parameters

`eventInfo`  
An object based on the [`RTCTrackEventInit`](../rtctrackeventinit) dictionary, providing information about the track which has been added to the [`RTCPeerConnection`](../rtcpeerconnection). This object has the following properties:  

[`receiver`](../rtctrackeventinit/receiver)  
The [`RTCRtpReceiver`](../rtcrtpreceiver) which is being used to receive the track's media.

 [`streams`](../rtctrackeventinit/streams) <span class="badge inline optional">Optional</span>   
An array of [`MediaStream`](../mediastream) objects representing each of the streams that comprise the event's corresponding track.

[`track`](../rtctrackeventinit/track)  
The [`MediaStreamTrack`](../mediastreamtrack) the event is associated with.

[`transceiver`](transceiver)  
The [`RTCRtpTransceiver`](../rtcrtptransceiver) associated with the event.

### Return value

A new [`RTCTrackEvent`](../rtctrackevent) describing a track which has been added to the `RTCPeerConnection`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#constructors-3">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCTrackEvent()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCTrackEvent.RTCTrackEvent`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/RTCTrackEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/RTCTrackEvent</a>
