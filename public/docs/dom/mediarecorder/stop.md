# MediaRecorder.stop()

The `MediaRecorder.stop()` method (part of the [MediaRecorder API](../mediastream_recording_api)) is used to stop media capture.

When the `stop()` method is invoked, the UA queues a task that runs the following steps:

1.  If [`MediaRecorder.state`](state) is "inactive", raise a DOM `InvalidState` error and terminate these steps. If the [`MediaRecorder.state`](state) is not "inactive", continue on to the next step.
2.  Set the [`MediaRecorder.state`](state) to "inactive" and stop capturing media.
3.  Raise a `dataavailable` event containing the Blob of data that has been gathered.
4.  Raise a `stop` event.

## Syntax

    MediaRecorder.stop()

### Errors

An `InvalidState` error is raised if the `stop()` method is called while the `MediaRecorder` object’s [`MediaRecorder.state`](state) is "inactive" — it makes no sense to stop media capture if it is already stopped.

## Example

    ...

      stop.onclick = function() {
        mediaRecorder.stop();
        console.log("recorder stopped, data available");
      }

    ...

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-stop">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.stop()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`stop`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/stop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/stop</a>
