TextTrackList: addtrack event
=============================

The `addtrack` event is fired when a track is added to a `TextTrackList`.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../trackevent"><code>TrackEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onaddtrack</code></td></tr></tbody></table>

Examples
--------

Using `addEventListener()`:

    const mediaElement = document.querySelector('video, audio');

    mediaElement.textTracks.addEventListener('addtrack', (event) => {
      console.log(`Text track: ${event.track.label} added`);
    });

Using the `onaddtrack` event handler property:

    const mediaElement = document.querySelector('video, audio');

    mediaElement.textTracks.onaddtrack = (event) => {
      console.log(`Text track: ${event.track.label} added`);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#event-media-addtrack">HTML Living Standard<br />
<span class="small">The definition of 'addtrack' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`addtrack_event`

Yes

≤79

?

?

?

?

Yes

Yes

?

?

?

Yes

See also
--------

-   Related events: `removetrack`, `change`
-   This event on `VideoTrackList` targets: `addtrack`
-   This event on `AudioTrackList` targets: `addtrack`
-   This event on `MediaStream` targets: `addtrack`
-   [Media Streams API](../media_streams_api)
-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList/addtrack_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList/addtrack_event</a>
