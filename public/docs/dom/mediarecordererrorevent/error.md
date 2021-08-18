MediaRecorderErrorEvent.error
=============================

The read-only `error` property in the **[`MediaRecorderErrorEvent`](../mediarecordererrorevent)** interface is a [`DOMException`](../domexception) object providing details about the exception that was thrown by a [`MediaRecorder`](../mediarecorder) instance.

When a `MediaRecorderErrorEvent` occurs, you can determine to some extent what went wrong by examining the `error` property within the `MediaRecorderErrorEvent` received by the `MediaRecorder`'s `error` event handler, [`onerror`](../mediarecorder/onerror).

Syntax
------

    error = MediaRecorderErrorEvent.error;

### Value

A [`DOMException`](../domexception) describing the error represented by the event. The error's [`name`](../domexception/name) property's value may be any exception that makes sense during the handling of media recording, including these specifically identified by the specification. The descriptions here are generic ones; you'll find more specific ones to various scenarios in which they may occur in the corresponding method references.

`InvalidStateError`  
An operation was attempted in a context in which it isn't allowed, or a request has been made on an object that's deleted or removed.

`NotSupportedError`  
A `MediaRecorder` couldn't be created because the specified options weren't valid. The `message` atttribute should provide additional information, if it exists.

`SecurityError`  
The [`MediaStream`](../mediastream) is configured to disallow recording. This may be the case, for example, with sources obtained using [`getUserMedia()`](../mediadevices/getusermedia) when the user denies permission to use an input device. This also happens when a [`MediaStreamTrack`](../mediastreamtrack) within the stream is marked as <span class="page-not-created">`isolated`</span> due to the <span class="page-not-created">`peerIdentity`</span> constraint on the source stream.

`InvalidModificationError`  
The number of tracks on the stream being recorded has changed. You can't add or remove tracks while recording media.

`UnknownError`  
A non-security related error occurred that cannot otherwise be categorized. Recording stops, the `MediaRecorder`'s [`state`](../mediarecorder/state) becomes `inactive`, one last `dataavailable` event is sent to the `MediaRecorder` with the remaining received data, and finally a `stop` event is sent.

Examples
--------

### Basic error-handling example

This function creates and returns a `MediaRecorder` for a given [`MediaStream`](../mediastream), configured to buffer data into an array and to watch for errors.

    function recordStream(stream) {
      let recorder = null;
      let bufferList = [];

      try {
        recorder = new MediaRecorder(stream);
      } catch(err) {
        /* exception while trying to create the recorder; handle that */
      }

      recorder.ondataavailable = function(event) {
        bufferList.push(event.data);
      };

      recorder.onerror = function(event) {
        let error = event.error;
      };

      recorder.start(100);  /* 100ms time slices per buffer */
      return recorder;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#errorevent-section">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorderErrorEvent.error' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`error`

No

Uses a generic event with an `error` property.

No

Uses a generic event with an `error` property.

57

No

No

Uses a generic event with an `error` property.

14

No

No

Uses a generic event with an `error` property.

57

No

Uses a generic event with an `error` property.

14

No

Uses a generic event with an `error` property.

See also
--------

-   [MediaStream Recording API](../mediastream_recording_api)
-   [Using the MediaStream Recording API](../mediastream_recording_api/using_the_mediastream_recording_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorderErrorEvent/error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorderErrorEvent/error</a>
