# MediaStream.getVideoTracks()

The `getVideoTracks()` method of the [`MediaStream`](../mediastream) interface returns a sequence of [`MediaStreamTrack`](../mediastreamtrack) objects representing the video tracks in this stream.

## Syntax

    var mediaStreamTracks[] = mediaStream.getVideoTracks();

### Parameters

None.

### Return value

An array of [`MediaStreamTrack`](../mediastreamtrack) objects, one for each video track contained in the media stream. Video tracks are those tracks whose [`kind`](../mediastreamtrack/kind) property is `video`. The array is empty if the stream contains no video tracks.

**Note:** The order of the tracks is not defined by the specification, and may not be the same from one call to `getVideoTracks()` to another.

Early versions of this API included a special `VideoStreamTrack` interface which was used as the type for each entry in the list of video streams; however, this has since been merged into the main [`MediaStreamTrack`](../mediastreamtrack) interface.

## Example

The following example, extracted from [Chrome's Image Capture / Photo Resolution Sample](https://googlechrome.github.io/samples/image-capture/photo-resolution.html), uses `getVideoTracks()` to retrieve a track for passing to the [`ImageCapture()`](../imagecapture/imagecapture) constructor.

    var imageCapture;

    navigator.mediaDevices.getUserMedia({video: true})
    .then(mediaStream => {
      document.querySelector('video').srcObject = mediaStream;

      const track = mediaStream.getVideoTracks()[0];
      imageCapture = new ImageCapture(track);

      return imageCapture.getPhotoCapabilities();
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastream-getvideotracks">Media Capture and Streams<br />
<span class="small">The definition of 'getVideoTracks()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getVideoTracks`

26

12

22

Prior to Firefox 64, this method returned an array of `VideoStreamTrack` objects. However, `MediaStreamTrack` has now subsumed that interface's functionality.

No

Yes

11

37

26

22

Prior to Firefox 64, this method returned an array of `VideoStreamTrack` objects. However, `MediaStreamTrack` has now subsumed that interface's functionality.

No

11

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/getVideoTracks" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/getVideoTracks</a>
