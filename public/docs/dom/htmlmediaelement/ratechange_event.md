# HTMLMediaElement: ratechange event

The `ratechange` event is fired when the playback rate has changed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Target</td><td>Element</td></tr><tr class="odd"><td>Default Action</td><td>None</td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>GlobalEventHandlers.onratechange</code></span></td></tr><tr class="odd"><td>Specification</td><td><a href="https://www.whatwg.org/specs/web-apps/current-work/multipage/the-video-element.html#event-media-playing">HTML5 media</a></td></tr></tbody></table>

## Examples

These examples add an event listener for the HTMLMediaElement's `ratechange` event, then post a message when that event handler has reacted to the event firing.

Using `addEventListener()`:

    const video = document.querySelector('video');

    video.addEventListener('ratechange', (event) => {
      console.log('The playback rate changed.');
    });

Using the `onratechange` event handler property:

    const video = document.querySelector('video');

    video.onratechange = (event) => {
      console.log('The playback rate changed.');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#event-media-ratechange">HTML Living Standard<br />
<span class="small">The definition of 'ratechange media event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#event-media-ratechange">HTML5<br />
<span class="small">The definition of 'ratechange media event' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td></tr></tbody></table>

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

`ratechange_event`

3

12

3.5

9

10.5

3.1

≤37

18

4

Yes

Yes

1.0

## Related Events

- [`HTMLMediaElement: playing event`](playing_event)
- [`HTMLMediaElement: waiting event`](waiting_event)
- [`HTMLMediaElement: seeking event`](seeking_event)
- [`HTMLMediaElement: seeked event`](seeked_event)
- [`HTMLMediaElement: ended event`](ended_event)
- [`HTMLMediaElement: loadedmetadata event`](loadedmetadata_event)
- [`HTMLMediaElement: loadeddata event`](loadeddata_event)
- [`HTMLMediaElement: canplay event`](canplay_event)
- [`HTMLMediaElement: canplaythrough event`](canplaythrough_event)
- [`HTMLMediaElement: durationchange event`](durationchange_event)
- [`HTMLMediaElement: timeupdate event`](timeupdate_event)
- [`HTMLMediaElement: play event`](play_event)
- [`HTMLMediaElement: pause event`](pause_event)
- [`HTMLMediaElement: ratechange event`](ratechange_event)
- [`HTMLMediaElement: volumechange event`](volumechange_event)
- [`HTMLMediaElement: suspend event`](suspend_event)
- [`HTMLMediaElement: emptied event`](emptied_event)
- [`HTMLMediaElement: stalled event`](stalled_event)

## See also

- [`HTMLAudioElement`](../htmlaudioelement)
- [`HTMLVideoElement`](../htmlvideoelement)
- [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
- [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/ratechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/ratechange_event</a>
