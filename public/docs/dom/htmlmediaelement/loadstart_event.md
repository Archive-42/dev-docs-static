HTMLMediaElement: loadstart event
=================================

The `loadstart` event is fired when the browser has started to load a resource.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onloadstart"><code>onloadstart</code></a></td></tr></tbody></table>

Examples
--------

### Live example

#### HTML

    <div class="example">

        <button type="button">Load video</button>
        <video controls width="250"></video>

        <div class="event-log">
            <label>Event log:</label>
            <textarea readonly class="event-log-contents"></textarea>
        </div>

    </div>

#### JS

    const loadVideo = document.querySelector('button');
    const video = document.querySelector('video');
    const eventLog = document.querySelector('.event-log-contents');
    let source = null;

    function handleEvent(event) {
        eventLog.textContent = eventLog.textContent + `${event.type}\n`;
    }

    video.addEventListener('loadstart', handleEvent);
    video.addEventListener('progress', handleEvent);
    video.addEventListener('canplay', handleEvent);
    video.addEventListener('canplaythrough', handleEvent);

    loadVideo.addEventListener('click', () => {

        if (source) {
            document.location.reload();
        } else {
            loadVideo.textContent = "Reset example";
            source = document.createElement('source');
            source.setAttribute('src', 'https://interactive-examples.mdn.mozilla.net/media/examples/flower.webm');
            source.setAttribute('type', 'video/webm');

            video.appendChild(source);
        }
    });

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#event-media-loadstart">HTML Living Standard<br />
<span class="small">The definition of 'loadstart media event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#event-media-loadstart">HTML5<br />
<span class="small">The definition of 'loadstart media event' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td></tr></tbody></table>

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

`loadstart_event`

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

See also
--------

-   [`HTMLAudioElement`](../htmlaudioelement)
-   [`HTMLVideoElement`](../htmlvideoelement)
-   [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
-   [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/loadstart_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/loadstart_event</a>
