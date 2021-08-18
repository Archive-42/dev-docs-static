# ImageCapture() constructor

The `ImageCapture()` constructor creates a new [`ImageCapture`](../imagecapture) object.

## Syntax

    const imageCapture = new ImageCapture(videoTrack)

### Parameters

`videoTrack`  
A [`MediaStreamTrack`](../mediastreamtrack) from which the still images will be taken. This can be any source, such as an incoming stream of a video conference, a playing movie, or the stream from a webcam.

### Return value

A new `ImageCapture` object which can be used to capture still frames from the specified video track.

## Example

The following example shows how to use a call to [`MediaDevices.getUserMedia()`](../mediadevices/getusermedia) to retrieve the [`MediaStreamTrack`](../mediastreamtrack) needed by the `ImageCapture()` constructor.

     navigator.mediaDevices.getUserMedia({video: true})
      .then(mediaStream => {
        document.querySelector('video').srcObject = mediaStream
        const track = mediaStream.getVideoTracks()[0];
        imageCapture = new ImageCapture(track);
      })
      .catch(error => console.log(error));

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-image/#dom-imagecapture-imagecapture">MediaStream Image Capture<br />
<span class="small">The definition of 'ImageCapture' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ImageCapture`

59

≤79

No

See [bug 888177](https://bugzil.la/888177).

No

46

No

59

59

No

See [bug 888177](https://bugzil.la/888177).

43

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageCapture/ImageCapture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageCapture/ImageCapture</a>
