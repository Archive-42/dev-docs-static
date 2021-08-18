# HTMLMediaElement: abort event

The `abort` event is fired when the resource was not fully loaded, but not as the result of an error.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onabort"><code>onabort</code></a></td></tr></tbody></table>

## Examples

    const video = document.querySelector('video');
    const videoSrc = 'https://path/to/video.webm';

    video.addEventListener('abort', () => {
      console.log(`Abort loading: ${videoSrc}`);
    });

    const source = document.createElement('source');
    source.setAttribute('src', videoSrc);
    source.setAttribute('type', 'video/webm');

    video.appendChild(source);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#event-media-abort">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#event-media-abort">HTML5</a></td><td><span class="spec-rec">Recommendation</span></td></tr></tbody></table>

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

`abort_event`

Yes

≤79

Yes

?

Yes

?

Yes

Yes

Yes

?

?

Yes

## See also

- [`HTMLAudioElement`](../htmlaudioelement)
- [`HTMLVideoElement`](../htmlvideoelement)
- [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
- [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/abort_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/abort_event</a>
