RTCTrackEvent
=============

The [WebRTC API](webrtc_api) interface `RTCTrackEvent` represents the `track` event, which is sent when a new [`MediaStreamTrack`](mediastreamtrack) is added to an [`RTCRtpReceiver`](rtcrtpreceiver) which is part of the [`RTCPeerConnection`](rtcpeerconnection). The target is the `RTCPeerConnection` object to which the track is being added.

This event is sent by the WebRTC layer to the web site or application, so you will not typically need to instantiate an `RTCTrackEvent` yourself.

Constructor
-----------

[`RTCTrackEvent()`](rtctrackevent/rtctrackevent)  
Creates and returns a new `RTCTrackEvent` object, initialized with properties taken from the specified [`RTCTrackEventInit`](rtctrackeventinit) dictionary. You will probably not need to create new track events yourself, since they're typically created by the WebRTC infrastructure and sent to the connection's [`ontrack`](rtcpeerconnection/ontrack) event handler.

Properties
----------

*Since `RTCTrackEvent` is based on [`Event`](event), its properties are also available.*

 [`receiver`](rtctrackevent/receiver) <span class="badge inline readonly">Read only </span>   
The [`RTCRtpReceiver`](rtcrtpreceiver) used by the track that's been added to the `RTCPeerConnection`.

 [`streams`](rtctrackevent/streams) <span class="badge inline readonly">Read only </span> <span class="badge inline optional">Optional</span>   
An array of [`MediaStream`](mediastream) objects, each representing one of the media streams to which the added [`track`](rtctrackevent/track) belongs. By default, the array is empty, indicating a streamless track.

 [`track`](rtctrackevent/track) <span class="badge inline readonly">Read only </span>   
The [`MediaStreamTrack`](mediastreamtrack) which has been added to the connection.

 [`transceiver`](rtctrackevent/transceiver) <span class="badge inline readonly">Read only </span>   
The [`RTCRtpTransceiver`](rtcrtptransceiver) being used by the new track.

Track event types
-----------------

There is only one type of track event.

### `track`

The [`track`](rtcpeerconnection/track_event) event is sent to the [`RTCPeerConnection`](rtcpeerconnection) when a new track has been added to the connection. By the time the `track` event is delivered to the `RTCPeerConnection`'s [`ontrack`](rtcpeerconnection/ontrack) handler, the new media has completed its negotiation for a specific [`RTCRtpReceiver`](rtcrtpreceiver) (which is specified by the event's [`receiver`](rtctrackevent/receiver) property).

In addition, the [`MediaStreamTrack`](mediastreamtrack) specified by the receiver's [`track`](rtcrtpreceiver/track) is the same one specified by the event's [`track`](rtctrackevent/track), and the track has been added to any associated remote [`MediaStream`](mediastream) objects.

You can add a `track` event listener to be notified when the new track is available so that you can, for example, attach its media to a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, using either [`RTCPeerConnection.addEventListener()`](eventtarget/addeventlistener) or the `ontrack` event handler property.

**Note:** It may be helpful to keep in mind that you receive the `track` event when a new inbound track has been added to your connection, and you call [`addTrack()`](rtcpeerconnection/addtrack) to add a track to the far end of the connection, thereby triggering a `track` event on the remote peer.

Example
-------

This simple example creates an event listener for the [`track`](rtcpeerconnection/track_event) event which sets the [`srcObject`](htmlmediaelement/srcobject) of the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element with the ID `videobox` to the first stream in the list passed in the event's [`streams`](rtctrackevent/streams) array.

    peerConnection.addEventListener("track", e => {
      let videoElement = document.getElementById("videobox");
      videoElement.srcObject = e.streams[0];
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtctrackevent">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCTrackEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`RTCTrackEvent`

56

≤18

22

No

43

11

56

56

44

43

11

6.0

`receiver`

56

≤18

22

No

43

11

56

56

44

43

11

6.0

`streams`

56

≤18

22

No

43

11

56

56

44

43

11

6.0

`track`

56

≤18

22

No

43

11

56

56

44

43

11

6.0

`transceiver`

69

≤18

59

No

43

11

69

69

59

43

11

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent</a>
