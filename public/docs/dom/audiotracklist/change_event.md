# AudioTrackList: change event

The `change` event is fired when an audio track is enabled or disabled, for example by changing the track's `enabled` property.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onchange"><code>onchange</code></a></td></tr></tbody></table>

## Examples

Using `addEventListener()`:

    const videoElement = document.querySelector('video');
    videoElement.audioTracks.addEventListener('change', (event) => {
        console.log(`'${event.type}' event fired`);
    });

    // changing the value of `enabled` will trigger the `change` event
    const toggleTrackButton = document.querySelector('.toggle-track');
    toggleTrackButton.addEventListener('click', () => {
      const track = videoElement.audioTracks[0];
      track.enabled = !track.enabled;
    });

Using the `onchange` event handler property:

    const videoElement = document.querySelector('video');
    videoElement.audioTracks.onchange = (event) => {
        console.log(`'${event.type}' event fired`);
    };

    // changing the value of `enabled` will trigger the `change` event
    const toggleTrackButton = document.querySelector('.toggle-track');
    toggleTrackButton.addEventListener('click', () => {
      const track = videoElement.audioTracks[0];
      track.enabled = !track.enabled;
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#event-media-change">HTML Living Standard<br />
<span class="small">The definition of 'change' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`change_event`

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

- Related events: `addtrack`, `removetrack`
- This event on `VideoTrackList` targets: `change`
- [Media Streams API](../media_streams_api)
- [WebRTC API](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/change_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/change_event</a>
