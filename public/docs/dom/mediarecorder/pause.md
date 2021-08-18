MediaRecorder.pause()
=====================

The `Media.pause()` method (part of the [MediaRecorder API](../mediastream_recording_api)) is used to pause recording of media streams.

When a `MediaRecorder` object’s `pause()`method is called, the browser queues a task that runs the below steps:

1.  If [`MediaRecorder.state`](state) is "inactive", raise a DOM `InvalidState` error and terminate these steps. If not, continue to the next step.
2.  Set [`MediaRecorder.state`](state) to "paused".
3.  Stop gathering data into the current [`Blob`](../blob), but keep it available so that recording can be resumed later on.
4.  Raise a `pause` event.

Syntax
------

    MediaRecorder.pause()

### Return value

`undefined`.

### Exceptions

`InvalidStateError`  
The `MediaRecorder` is currently `"inactive"`; you can't pause recording if it's not active. If you call `pause()` while already paused, it silently does nothing.

Example
-------

    ...

     pause.onclick = function() {
         mediaRecorder.pause();
         console.log("recording paused");
     }

    ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-pause">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.pause()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`pause`

49

79

25

No

36

14.1

49

49

25

36

14.5

5.0

See also
--------

-   [Using the MediaRecorder API](../mediastream_recording_api/using_the_mediastream_recording_api)
-   [Web Dictaphone](https://mdn.github.io/web-dictaphone/): MediaRecorder + getUserMedia + Web Audio API visualization demo, by [Chris Mills](https://twitter.com/chrisdavidmills) ([source on Github](https://github.com/mdn/web-dictaphone/).)
-   [simpl.info MediaStream Recording demo](https://simpl.info/mediarecorder/), by [Sam Dutton](https://twitter.com/sw12).
-   [`Navigator.getUserMedia`](../navigator/getusermedia)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/pause" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/pause</a>
