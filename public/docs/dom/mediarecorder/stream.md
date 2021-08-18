MediaRecorder.stream
====================

The `MediaRecorder.stream` read-only property returns the stream that was passed into the `MediaRecorder()` constructor when the `MediaRecorder` was created.

Syntax
------

    var stream = MediaRecorder.stream

### Values

The MediaStream passed into the `MediaRecorder()` constructor when the `MediaRecorder` was originally created.

Example
-------

    if (navigator.getUserMedia) {
       console.log('getUserMedia supported.');
       navigator.getUserMedia (
          // constraints - only audio needed for this app
          {
             audio: true
          },

          // Success callback
          function(stream) {
               var mediaRecorder = new MediaRecorder(stream);

               var myStream = mediaRecorder.stream;
               console.log(myStream);

    ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-stream">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.stream' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`stream`

49

47-49

Prior to Chrome 49, only video is supported, not audio.

79

25

No

36

14

49

49

47-49

Prior to Chrome 49, only video is supported, not audio.

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/stream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/stream</a>
