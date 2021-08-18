# MediaRecorder: error event

The [`MediaRecorder`](../mediarecorder) interface's `error` event is fired when an error occurs: for example because recording wasn't allowed or was attempted using an unsupported codec.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../mediarecordererrorevent"><code>MediaRecorderErrorEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onerror</code></td></tr></tbody></table>

For details of the all the possible errors see the documentation for the event handler property: `onerror`.

## Examples

Using `addEventListener` to listen for `error` events:

    async function record() {
        const stream = await navigator.mediaDevices.getUserMedia({audio: true});
        const recorder = new MediaRecorder(stream);
        recorder.addEventListener('error', (event) => {
            console.error(`error recording stream: ${event.error.name}`)
        });
        recorder.start();
    }

    record();

The same, but using the onerror event handler property:

    async function record() {
        const stream = await navigator.mediaDevices.getUserMedia({audio: true});
        const recorder = new MediaRecorder(stream);
        recorder.onerror = (event) => {
            console.error(`error recording stream: ${event.error.name}`)
        };
        recorder.start();
    }

    record();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#errorevent-section">MediaStream Recording</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`error_event`

49

79

25

No

36

14

49

49

25

36

14

5.0

## See also

- [Using the MediaRecorder API](../mediastream_recording_api/using_the_mediastream_recording_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/error_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/error_event</a>
