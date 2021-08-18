MediaStream: addtrack event
===========================

The `addtrack` event is fired when a new `MediaStreamTrack` object has been added to a `MediaStream`.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../mediastreamtrackevent"><code>MediaStreamTrackEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onaddtrack</code></td></tr></tbody></table>

Examples
--------

Using `addEventListener()`:

    let stream = new MediaStream();

    stream.addEventListener('addtrack', (event) => {
      console.log(`New ${event.track.kind} track added`);
    });

Using the `onaddtrack` event handler property:

    let stream = new MediaStream();

    stream.onaddtrack = (event) => {
      console.log(`New ${event.track.kind} track added`);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#event-mediastream-addtrack">Media Capture and Streams<br />
<span class="small">The definition of 'addtrack' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td></tr></tbody></table>

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

12

50

No

No

Yes

Yes

Yes

50

No

Yes

Yes

See also
--------

-   Related events: `removetrack`
-   This event on `AudioTrackList` targets: `addtrack`
-   This event on `VideoTrackList` targets: `addtrack`
-   [Media Streams API](../media_streams_api)
-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/addtrack_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/addtrack_event</a>
