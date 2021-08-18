MediaStream: removetrack event
==============================

The `removetrack` event is fired when a new `MediaStreamTrack` object has been removed from a `MediaStream`.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../mediastreamtrackevent"><code>MediaStreamTrackEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onremovetrack</code></td></tr></tbody></table>

Examples
--------

Using `addEventListener()`:

    let stream = new MediaStream();

    stream.addEventListener('removetrack', (event) => {
      console.log(`${event.track.kind} track removed`);
    });

Using the `onremovetrack` event handler property:

    let stream = new MediaStream();

    stream.onremovetrack = (event) => {
      console.log(`${event.track.kind} track removed`);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#event-mediastream-removetrack">Media Capture and Streams<br />
<span class="small">The definition of 'removetrack' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td></tr></tbody></table>

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

`removetrack_event`

Yes

12

No

No

No

Yes

Yes

Yes

No

No

Yes

Yes

See also
--------

-   Related events: `addtrack`
-   This event on `AudioTrackList` targets: `removetrack`
-   This event on `VideoTrackList` targets: `removetrack`
-   [Media Streams API](../media_streams_api)
-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/removetrack_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/removetrack_event</a>
