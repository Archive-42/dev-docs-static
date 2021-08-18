MediaRecorder.onerror
=====================

The [`MediaRecorder`](../mediarecorder) interface's `onerror` event handler is called by the [MediaStream Recording API](../mediastream_recording_api) when an error occurs. You can provide an event handler to deal with errors that occur while creating or using a media recorder. The error object is of type [`MediaRecorderErrorEvent`](../mediarecordererrorevent), and its [`error`](../mediarecordererrorevent/error) property contains a [`DOMException`](../domexception) object that describes the error that occurred.

Syntax
------

    MediaRecorder.onerror = errorHandlerFunction;

### Value

A function to be called whenever an error occurs during the recorder's lifetime. In addition to other general errors that might occur, the following errors are specifically possible when using the MediaStream Recording API; to determine which occurred, check the value of [`MediaRecorderErrorEvent.error.name`](../domexception/name).

`InvalidStateError`  
An attempt was made to stop or pause or an inactive recorder, start or resume an active recorder, or otherwise manipulate the `MediaRecorder` while in the wrong state. This exception can also occur when a request is made on a source that has been deleted or removed.

`SecurityError`  
The [`MediaStream`](../mediastream) is configured to disallow recording. This may be the case, for example, with sources obtained using [`getUserMedia()`](../mediadevices/getusermedia) when the user denies permission to use an input device. This also happens when a [`MediaStreamTrack`](../mediastreamtrack) within the stream is marked as <span class="page-not-created">`isolated`</span> due to the <span class="page-not-created">`peerIdentity`</span> constraint on the source stream.

`NotSupportedError`  
An attempt was made to instantiate a `MediaRecorder` using a MIME type that isn't supported on the user's device; one or more of the requested container, codecs, or profiles as well as other information may be invalid.

`InvalidModificationError`  
The number of tracks on the stream being recorded has changed. You can't add or remove tracks while recording media.

`UnknownError`  
An non-security related error occurred that cannot otherwise be categorized. Recording stops, the `MediaRecorder`'s [`state`](state) becomes `inactive`, one last `dataavailable` event is sent to the `MediaRecorder` with the remaining received data, and finally a `stop` event is sent.

These errors may occur either directly because of a call to a `MediaRecorder` method, or indirectly due to a problem arising during the recording process.

Example
-------

This example creates a new [`MediaRecorder`](../mediarecorder) instance and starts recording using the [user agent's](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) default media format. It returns either the `MediaRecorder` or the name of the error that occurred if any exceptions are thrown during the setup process.

    function recordStream(stream) {
      let recorder = null;
      let bufferList = [];

      try {
        recorder = new MediaRecorder(stream);
      } catch(err) {
        return err.name;     /* return the error name */
      }

      recorder.ondataavailable = function(event) {
        bufferList.push(event.data);
      };

      recorder.onerror = function(event) {
        let error = event.error;

        switch(error.name) {
          case InvalidStateError:
            showNotification("You can't record the video right " +
                             "now. Try again later.");
            break;
          case SecurityError:
            showNotification("Recording the specified source " +
                             "is not allowed due to security " +
                             "restrictions.");
            break;
          default:
            showNotification("A problem occurred while trying " +
                             "to record the video.");
            break;
        }
      };

      /* this would be a good place to create a Worker to handle
         writing the buffers to disk periodically */

      recorder.start(100);  /* 100ms time slices per buffer */
      return recorder;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-onerror">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.onerror' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onerror`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onerror</a>
