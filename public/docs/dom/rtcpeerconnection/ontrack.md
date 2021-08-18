RTCPeerConnection.ontrack
=========================

The [`RTCPeerConnection`](../rtcpeerconnection) property `ontrack` is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function to be called when the `track` event occurs, indicating that a track has been added to the [`RTCPeerConnection`](../rtcpeerconnection). The function receives as input the event object, of type [`RTCTrackEvent`](../rtctrackevent); this event is sent when a new incoming [`MediaStreamTrack`](../mediastreamtrack) has been created and associated with an [`RTCRtpReceiver`](../rtcrtpreceiver) object which has been added to the set of receivers on connection.

Syntax
------

    RTCPeerConnection.ontrack = eventHandler;

### Value

Set `ontrack` to be a function you provide that accepts as input a [`RTCTrackEvent`](../rtctrackevent) object describing the new track and how it's being used. This information includes the [`MediaStreamTrack`](../mediastreamtrack) object representing the new track, the [`RTCRtpReceiver`](../rtcrtpreceiver) and [`RTCRtpTransceiver`](../rtcrtptransceiver), and a list of [`MediaStream`](../mediastream) objects which indicates which stream or streams the track is part of..

Example
-------

This example, taken from the code for the article [Signaling and video calling](../webrtc_api/signaling_and_video_calling), connects the incoming track to the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element which will be used to display the incoming video.

    pc.ontrack = function(event) {
      document.getElementById("received_video").srcObject = event.streams[0];
      document.getElementById("hangup-button").disabled = false;
    };

The first line of our `ontrack` event handler takes the first stream in the incoming track and sets the [`srcobject`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-srcobject) attribute to that. This connects that stream of video to the element so that it begins to be presented to the user. The second line of code enables a "hang up" button, which the user can use to disconnect from the call.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-ontrack">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.ontrack' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`ontrack`

64

79

22

No

43

Promise-based version.

37-43

11

64

64

44

43

Promise-based version.

37-43

11

6.0

See also
--------

-   The `track` event and its type, [`RTCTrackEvent`](../rtctrackevent).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/ontrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/ontrack</a>
