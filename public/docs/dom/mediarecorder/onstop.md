MediaRecorder.onstop
====================

The `MediaRecorder.onstop `event handler (part of the [MediaRecorder API](../mediastream_recording_api)) handles the `stop` event, allowing you to run code in response to media recording via a `MediaRecorder` being stopped.

The `stop` event is thrown either as a result of the [`MediaRecorder.stop()`](stop) method being invoked, or when the media stream being captured ends. In each case, the `stop` event is preceded by a `dataavailable` event, making the [`Blob`](../blob) captured up to that point available for you to use in your application.

Syntax
------

    MediaRecorder.onstop = function(event) { ... }
    MediaRecorder.addEventListener('stop', function(event) { ... })

Example
-------

    ...

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-onstop">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.onstop' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onstop`

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

See also
--------

-   [Using the MediaRecorder API](../mediastream_recording_api/using_the_mediastream_recording_api)
-   [Web Dictaphone](https://mdn.github.io/web-dictaphone/): MediaRecorder + getUserMedia + Web Audio API visualization demo, by [Chris Mills](https://twitter.com/chrisdavidmills) ([source on Github](https://github.com/mdn/web-dictaphone/).)
-   [simpl.info MediaStream Recording demo](https://simpl.info/mediarecorder/), by [Sam Dutton](https://twitter.com/sw12).
-   [`Navigator.getUserMedia`](../navigator/getusermedia)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onstop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onstop</a>
