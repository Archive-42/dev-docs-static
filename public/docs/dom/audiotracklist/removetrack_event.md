# AudioTrackList: removetrack event

The `removetrack` event is fired when a track is removed from an `AudioTrackList`.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../trackevent"><code>TrackEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onremovetrack</code></td></tr></tbody></table>

## Examples

Using `addEventListener()`:

    const videoElement = document.querySelector('video');

    videoElement.audioTracks.addEventListener('removetrack', (event) => {
      console.log(`Audio track: ${event.track.label} removed`);
    });

Using the `onremovetrack` event handler property:

    const videoElement = document.querySelector('video');

    videoElement.audioTracks.onremovetrack = (event) => {
      console.log(`Audio track: ${event.track.label} removed`);
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#event-media-removetrack">HTML Living Standard<br />
<span class="small">The definition of 'removetrack' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`removetrack_event`

37

79

12-79

33

10

24

6.1

No

37

33

24

7

No

## See also

- Related events: `addtrack`, `change`
- This event on `VideoTrackList` targets: `removetrack`
- This event on `MediaStream` targets: `removetrack`
- [Media Streams API](../media_streams_api)
- [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/removetrack_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/removetrack_event</a>
