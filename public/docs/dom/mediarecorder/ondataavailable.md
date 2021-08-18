# MediaRecorder.ondataavailable

The `MediaRecorder.ondataavailable `event handler (part of the [MediaStream Recording API](../mediastream_recording_api)) handles the `dataavailable` event, letting you run code in response to [`Blob`](../blob) data being made available for use.

The `dataavailable` event is fired when the MediaRecorder delivers media data to your application for its use. The data is provided in a [`Blob`](../blob) object that contains the data. This occurs in four situations:

- When the media stream ends, any media data not already delivered to your `ondataavailable` handler is passed in a single [`Blob`](../blob).
- When [`MediaRecorder.stop()`](stop) is called, all media data which has been captured since recording began or the last time a `dataavailable` event occurred is delivered in a [`Blob`](../blob); after this, capturing ends.
- When [`MediaRecorder.requestData()`](requestdata) is called, all media data which has been captured since recording began or the last time a `dataavailable` event occurred is delivered; then a new `Blob` is created and media capture continues into that blob.
- If a `timeslice` property was passed into the [`MediaRecorder.start()`](start) method that started media capture, a `dataavailable` event is fired every `timeslice` milliseconds. That means that each blob will have a specific time duration (except the last blob, which might be shorter, since it would be whatever is left over since the last event). So if the method call looked like this — `recorder.start(1000);` — the `dataavailable` event would fire after each second of media capture, and our event handler would be called every second with a blob of media data that's one second long. You can use `timeslice` alongside [`MediaRecorder.stop()`](stop) and [`MediaRecorder.requestData()`](requestdata) to produce multiple same-length blobs plus other shorter blobs as well.

The [`Blob`](../blob) containing the media data is available in the `dataavailable` event's `data` property.

## Syntax

    MediaRecorder.ondataavailable = function(event) { ... }
    MediaRecorder.addEventListener('dataavailable', function(event) { ... })

## Example

    ...
      var chunks = [];

      mediaRecorder.onstop = function(e) {
        console.log("data available after MediaRecorder.stop() called.");

        var audio = document.createElement('audio');
        audio.controls = true;
        var blob = new Blob(chunks, { 'type' : 'audio/ogg; codecs=opus' });
        var audioURL = window.URL.createObjectURL(blob);
        audio.src = audioURL;
        console.log("recorder stopped");
      }

      mediaRecorder.ondataavailable = function(e) {
        chunks.push(e.data);
      }

    ...

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-ondataavailable">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.ondataavailable' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`ondataavailable`

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

- [Using the MediaStream Recording API](../mediastream_recording_api)
- [Web Dictaphone](https://mdn.github.io/web-dictaphone/): MediaRecorder + getUserMedia + Web Audio API visualization demo, by [Chris Mills](https://twitter.com/chrisdavidmills) ([source on Github](https://github.com/mdn/web-dictaphone/).)
- [simpl.info MediaStream Recording demo](https://simpl.info/mediarecorder/), by [Sam Dutton](https://twitter.com/sw12).
- [`Navigator.getUserMedia`](../navigator/getusermedia)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/ondataavailable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/ondataavailable</a>
