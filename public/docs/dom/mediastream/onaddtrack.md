# MediaStream.onaddtrack

The `MediaStream.onaddtrack` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function to be called when the `addtrack` event occurs on a [`MediaStream`](../mediastream) instance. This happens when a new track of any kind is added to the media stream. This event is fired when the browser adds a track to the stream (such as when a [`RTCPeerConnection`](../rtcpeerconnection) is renegotiated or a stream being captured using [`HTMLMediaElement.captureStream()`](../htmlmediaelement/capturestream) gets a new set of tracks because the media element being captured loaded a new source.

The `addtrack` event does _not_ get fired when JavaScript code explicitly adds tracks to the stream (by calling [`addTrack()`](addtrack)).

## Syntax

    MediaStream.onaddtrack = eventHandler;

### Value

This should be set to a function which you provide that accepts as input a [`MediaStreamTrackEvent`](../mediastreamtrackevent) object representing the `addtrack` event which has occurred. The [`MediaStreamTrack`](../mediastreamtrack) representing the track which was added is specified in the event's <span class="page-not-created">`track`</span> property.

## Example

This example adds a listener which, when a new track is added to the stream, appends a new item to a list of tracks; the new item shows the track's `kind` (`"audio"` or `"video"`) and `label`.

    stream.onaddtrack = function(event) {
      let trackList = document.getElementById("tracks");
      let label = document.createElement("li");

      label.innerHTML = event.track.kind + ": " + event.track.label;
      trackList.appendChild(label);
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#event-mediastream-addtrack">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStream.onaddtrack' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

## Browser compatibility

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

`onaddtrack`

26

12

50

No

No

11

37

26

50

No

11

1.5

## See also

- The `addtrack` event and its type, [`MediaStreamTrackEvent`](../mediastreamtrackevent).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/onaddtrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/onaddtrack</a>
