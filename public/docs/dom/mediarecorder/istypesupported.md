MediaRecorder.isTypeSupported
=============================

The `MediaRecorder.isTypeSupported()` static method returns a Boolean which is `true` if the MIME type specified is one the user agent should be able to successfully record.

Syntax
------

    var canRecord = MediaRecorder.isTypeSupported(mimeType)

### Parameters

`mimeType`  
The MIME media type to check.

### Return value

`true` if the [`MediaRecorder`](../mediarecorder) implementation is capable of recording [`Blob`](../blob) objects for the specified MIME type. Recording may still fail if there are insufficient resources to support the recording and encoding process. If the value is `false`, the user agent is incapable of recording the specified format.

Example
-------

    var types = ["video/webm",
                 "audio/webm",
                 "video/webm\;codecs=vp8",
                 "video/webm\;codecs=daala",
                 "video/webm\;codecs=h264",
                 "audio/webm\;codecs=opus",
                 "video/mpeg"];

    for (var i in types) {
      console.log( "Is " + types[i] + " supported? " + (MediaRecorder.isTypeSupported(types[i]) ? "Maybe!" : "Nope :("));
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-istypesupported">MediaStream Recording<br />
<span class="small">The definition of 'isTypeSupported()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`isTypeSupported`

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

See also
--------

-   [MediaStream Recording API](../mediastream_recording_api)
-   [Using the MediaStream Recording API](../mediastream_recording_api/using_the_mediastream_recording_api)
-   [Guide to media types and formats on the web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)
-   [The "codecs" parameter in common media types](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/codecs_parameter)
-   [`MediaStreamTrack`](../mediastreamtrack)
-   [`MediaStream`](../mediastream)
-   [`MediaCapabilities`](../mediacapabilities)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/isTypeSupported" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/isTypeSupported</a>
