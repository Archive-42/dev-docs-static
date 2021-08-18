# MediaRecorder.start()

The [`MediaRecorder`](../mediarecorder) method `start()`, which is part of the MediaStream Recording API, begins recording media into one or more [`Blob`](../blob) objects. You can record the entire duration of the media into a single `Blob` (or until you call [`requestData()`](requestdata)), or you can specify the number of milliseconds to record at a time. Then, each time that amount of media has been recorded, an event will be delivered to let you act upon the recorded media, while a new `Blob` is created to record the next slice of the media

Assuming the `MediaRecorder`'s [`state`](state) is `inactive`, `start()` sets the `state` to `recording`, then begins capturing media from the input stream. A `Blob` is created and the data is collected in it until the time slice period elapses or the source media ends. Each time a `Blob` is filled up to that point (the timeslice duration or the end-of-media, if no slice duration was provided), a `dataavailable` event is sent to the `MediaRecorder` with the recorded data. If the source is still playing, a new `Blob` is created and recording continues into that, and so forth.

When the source stream ends, `state` is set to `inactive` and data gathering stops. A final `dataavailable` event is sent to the `MediaRecorder`, followed by a `stop` event.

**Note**: If the browser is unable to start recording or continue recording, it will raise a [`DOMError`](../domerror) event, followed by a <span class="page-not-created">`MediaRecorder.dataavailable`</span> event containing the `Blob` it has gathered, followed by the [`MediaRecorder.stop`](stop) event.

## Syntax

    mediaRecorder.start(timeslice)

### Parameters

`timeslice` <span class="badge inline optional">Optional</span>  
The number of milliseconds to record into each [`Blob`](../blob). If this parameter isn't included, the entire media duration is recorded into a single `Blob` unless the [`requestData()`](requestdata) method is called to obtain the `Blob` and trigger the creation of a new `Blob` into which the media continues to be recorded.

### Return value

`undefined`.

### Exceptions

Errors that can be detected immediately are thrown as DOM exceptions. All other errors are reported through `error` events sent to the `MediaRecorder` object. You can implement the [`onerror`](onerror) event handler to respond to these errors.

`InvalidModificationError`  
The number of tracks on the stream being recorded has changed. You can't add or remove tracks while recording media.

`InvalidStateError`  
The `MediaRecorder` is not in the `inactive` state; you can't start recording media if it's already being recorded. See the [`state`](state) property.

`NotSupportedError`  
The media stream you're attempting to record is inactive, or one or more of the stream's tracks is in a format that can't be recorded using the current configuration.

`SecurityError`  
The [`MediaStream`](../mediastream) is configured to disallow recording. This may be the case, for example, with sources obtained using [`getUserMedia()`](../mediadevices/getusermedia) when the user denies permission to use an input device. This also happens when a [`MediaStreamTrack`](../mediastreamtrack) within the stream is marked as <span class="page-not-created">`isolated`</span> due to the <span class="page-not-created">`peerIdentity`</span> constraint on the source stream. This exception may also be delivered as an `error` event if the security options for the source media change after recording begins.

`UnknownError`  
Something else went wrong during the recording process.

## Example

    ...

      record.onclick = function() {
        mediaRecorder.start();
        console.log("recorder started");
      }

    ...

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-start">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.start()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`start`

47

79

25

No

36

14

47

47

25

36

14

5.0

## See also

- [Using the MediaRecorder API](../mediastream_recording_api/using_the_mediastream_recording_api)
- [Web Dictaphone](https://mdn.github.io/web-dictaphone/): MediaRecorder + getUserMedia + Web Audio API visualization demo, by [Chris Mills](https://twitter.com/chrisdavidmills) ([source on Github](https://github.com/mdn/web-dictaphone/).)
- [simpl.info MediaStream Recording demo](https://simpl.info/mediarecorder/), by [Sam Dutton](https://twitter.com/sw12).
- [`getUserMedia()`](../mediadevices/getusermedia)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/start" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/start</a>
