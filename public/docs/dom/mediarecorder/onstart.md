# MediaRecorder.onstart

The `MediaRecorder.onstart`event handler (part of the [MediaRecorder API](../mediastream_recording_api)) handles the `start` event, allowing you to run code in response to media recording being started by a `MediaRecorder`.

The `start` event is thrown as a result of the [`MediaRecorder.start()`](start) method being invoked. At this point, the data starts being gathered into a [`Blob`](../blob).

## Syntax

    MediaRecorder.onstart = function(event) { ... }
    MediaRecorder.addEventListener('start', function(event) { ... })

## Example

    ...

      record.onclick = function() {
        mediaRecorder.start();
        console.log("recorder started");
      }

      mediaRecorder.onstart = function() {
        // do something in response to
        // recording being started
      }

    ...

## Properties

None.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-onstart">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.onstart' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onstart`

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
- [Web Dictaphone](https://mdn.github.io/web-dictaphone/): MediaRecorder + getUserMedia + Web Audio API visualization demo, by [Chris Mills](https://twitter.com/chrisdavidmills) ([source on Github](https://github.com/mdn/web-dictaphone/).)
- [simpl.info MediaStream Recording demo](https://simpl.info/mediarecorder/), by [Sam Dutton](https://twitter.com/sw12).
- [`Navigator.getUserMedia`](../navigator/getusermedia)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onstart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onstart</a>
