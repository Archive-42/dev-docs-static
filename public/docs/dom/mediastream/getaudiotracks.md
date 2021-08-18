MediaStream.getAudioTracks()
============================

The **`getAudioTracks()`** method of the [`MediaStream`](../mediastream) interface returns a sequence that represents all the [`MediaStreamTrack`](../mediastreamtrack) objects in this stream's `track set` where [`MediaStreamTrack.kind`](../mediastreamtrack/kind) is `audio`.

Syntax
------

    var mediaStreamTracks = mediaStream.getAudioTracks()

### Parameters

None.

### Return value

An array of [`MediaStreamTrack`](../mediastreamtrack) objects, one for each audio track contained in the stream. Audio tracks are those tracks whose [`kind`](../mediastreamtrack/kind) property is `audio`. The array is empty if the stream contains no audio tracks.

**Note:** The order of the returned tracks is not defined by the specification and may, in fact, change from one call to `getAudioTracks()` to the next.

Early versions of this API included a special `AudioStreamTrack` interface which was used as the type for each entry in the list of audio streams; however, this has since been merged into the main [`MediaStreamTrack`](../mediastreamtrack) interface.

Example
-------

This example gets a webcam's audio and video in a stream using [`getUserMedia()`](../mediadevices/getusermedia), attaches the stream to a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, then sets a timer that, upon expiring, will stop the first audio track found on the stream.

    navigator.mediaDevices.getUserMedia({audio: true, video: true})
    .then(mediaStream => {
      document.querySelector('video').srcObject = mediaStream;
      // Stop the audio stream after 5 seconds
      setTimeout(() => {
        const tracks = mediaStream.getAudioTracks()
        tracks[0].stop()
      }, 5000)
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastream-getaudiotracks">Media Capture and Streams<br />
<span class="small">The definition of 'getAudioTracks()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getAudioTracks`

26

12

22

Prior to Firefox 64, this method returned an array of `AudioStreamTrack` objects. However, `MediaStreamTrack` has now subsumed that interface's functionality.

No

Yes

11

37

26

22

Prior to Firefox 64, this method returned an array of `AudioStreamTrack` objects. However, `MediaStreamTrack` has now subsumed that interface's functionality.

No

11

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/getAudioTracks" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/getAudioTracks</a>
