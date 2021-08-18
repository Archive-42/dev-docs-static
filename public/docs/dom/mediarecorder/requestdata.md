# MediaRecorder.requestData()

The `MediaRecorder.requestData()` method (part of the [MediaRecorder API](../mediastream_recording_api)) is used to raise a <span class="page-not-created">`dataavailable`</span> event containing a [`Blob`](../blob) object of the captured media as it was when the method was called. This can then be grabbed and manipulated as you wish.

When the `requestData()` method is invoked, the browser queues a task that runs the following steps:

1.  If [`MediaRecorder.state`](state) is "inactive", raise a DOM `InvalidState` error and terminate these steps. If [`MediaRecorder.state`](state) is not "inactive", continue to the next step.
2.  Raise a `dataavailable` event containing a [`Blob`](../blob) of the currently captured data (the Blob is available under the event's `data` attribute.)
3.  Create a new Blob and place subsequently captured data into it.

## Syntax

    MediaRecorder.requestData()

### Errors

An `InvalidState` error is raised if the `requestData()` method is called while the `MediaRecorder` object’s [`MediaRecorder.state`](state) is not "recording" — the media cannot be captured if recording is not occurring.

## Example

    ...

      captureMedia.onclick = function() {
        mediaRecorder.requestData();
        // makes snapshot available of data so far
        // ondataavailable fires, then capturing continues
        // in new Blob
      }

    ...

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-requestdata">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.requestData()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`requestData`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/requestData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/requestData</a>
