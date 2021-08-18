MediaRecorder.state
===================

The `MediaRecorder.state` read-only property returns the current state of the current `MediaRecorder` object.

Syntax
------

    var state = MediaRecorder.state

### Values

A [AnimationPlayState](https://w3c.github.io/web-animations/#enumdef-animationplaystate) object containing one of the following values:

<table><thead><tr class="header"><th>Enumeration</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code id="idl-def-RecordingStateEnum.inactive">inactive</code></td><td>Recording is not occurring — it has either not been started yet, or it has been started and then stopped.</td></tr><tr class="even"><td><code id="idl-def-RecordingStateEnum.recording">recording</code></td><td>Recording has been started and the UA is capturing data.</td></tr><tr class="odd"><td><code id="idl-def-RecordingStateEnum.paused">paused</code></td><td>Recording has been started, then paused, but not yet stopped or resumed.</td></tr></tbody></table>

Example
-------

    ...

      record.onclick = function() {
        mediaRecorder.start();
        console.log(mediaRecorder.state);
        // Will return "recording"
        console.log("recorder started");
      }

    ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-state">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.state' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`state`

49

47-49

Prior to Chrome 49, only video is supported, not audio.

79

25

No

36

14

49

47-49

Prior to Chrome 49, only video is supported, not audio.

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/state" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/state</a>
