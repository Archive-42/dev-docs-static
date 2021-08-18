TextTrackList: change event
===========================

The `change` event is fired when a text track is made active or inactive, or a [`textTrackList`](../texttracklist) is otherwise changed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onchange</code></td></tr></tbody></table>

Examples
--------

Using `addEventListener()`:

    const mediaElement = document.querySelectorAll('video, audio')[0];
    mediaElement.textTracks.addEventListener('change', (event) => {
        console.log(`'${event.type}' event fired`);
    });

Using the `onchange` event handler property:

    const mediaElement = document.querySelector('video, audio');
    mediaElement.textTracks.onchange = (event) => {
        console.log(`'${event.type}' event fired`);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#event-media-change">HTML Living Standard<br />
<span class="small">The definition of 'change' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`change_event`

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

-   Related events: `addtrack`, `removetrack`
-   This event on `VideoTrackList` targets: `change`
-   This event on `AudioTrackList` targets: `change`
-   [Media Streams API](../media_streams_api)
-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList/change_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList/change_event</a>
