MediaStream.onremovetrack
=========================

The `MediaStream.onremovetrack` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function to be called when the `removetrack` event occurs on a [`MediaStream`](../mediastream) instance. This happens when a track of any kind is removed from the media stream. This event is fired when the browser removes a track from the stream (such as when a [`RTCPeerConnection`](../rtcpeerconnection) is renegotiated or a stream being captured using [`HTMLMediaElement.captureStream()`](../htmlmediaelement/capturestream) gets a new set of tracks because the media element being captured loaded a new source.

The `removetrack` event does *not* get fired when JavaScript code explicitly removes tracks from the stream (by calling <span class="page-not-created">`removeTrack()`</span>).

Syntax
------

    MediaStream.onremovetrack = eventHandler;

### Value

This should be set to a function which you provide that accepts as input a [`MediaStreamTrackEvent`](../mediastreamtrackevent) object representing the `removetrack` event which has occurred. The [`MediaStreamTrack`](../mediastreamtrack) representing the track which was removed is specified in the event's <span class="page-not-created">`track`</span> property.

Example
-------

This example adds a listener which, when a track is removed from the stream, logs the track that was removed.

    stream.onremovetrack = function(event) {
      let trackList = document.getElementById("tracks");
      let label = document.createElement("li");

      label.textContent = `Removed: ${event.track.kind}: ${event.track.label}`;
      trackList.appendChild(label);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastream-onremovetrack">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStream.onremovetrack' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onremovetrack`

26

12

No

No

No

11

37

26

No

No

11

1.5

See also
--------

-   The `removetrack` event and its type, [`MediaStreamTrackEvent`](../mediastreamtrackevent).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/onremovetrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/onremovetrack</a>
