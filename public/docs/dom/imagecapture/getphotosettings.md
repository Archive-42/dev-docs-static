# ImageCapture.getPhotoSettings()

The `getPhotoSettings()` method of the [`ImageCapture`](../imagecapture) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a <span class="page-not-created">`PhotoSettings`</span> object containing the current photo configuration settings.

## Syntax

    const settingsPromise = imageCapture.getPhotoSettings()

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a <span class="page-not-created">`PhotoSettings`</span> object containing the following properties:

- `fillLightMode`: The flash setting of the capture device, one of `"auto"`, `"off"`, or `"on"`.
- `imageHeight`: The desired image height as an integer. The user agent selects the closest width value to this setting if it only supports discrete heights.
- `imageWidth`: The desired image width as an integer. The user agent selects the closest width value to this setting if it only supports discrete widths.
- `redEyeReduction`: A boolean indicating whether the red-eye reduction should be used if it is available.

## Example

The following example, extracted from [Chrome's Image Capture / Photo Resolution Sample](https://googlechrome.github.io/samples/image-capture/photo-resolution.html), uses the results from `getPhotoSettings()` to modify the size of an input range. This example also shows how the [`ImageCapture`](../imagecapture) object is created using a [`MediaStreamTrack`](../mediastreamtrack) retrieved from a device's [`MediaStream`](../mediastream).

    const input = document.querySelector('input[type="range"]');

    var imageCapture;

    navigator.mediaDevices.getUserMedia({video: true})
    .then(mediaStream => {
      document.querySelector('video').srcObject = mediaStream;

      const track = mediaStream.getVideoTracks()[0];
      imageCapture = new ImageCapture(track);

      return imageCapture.getPhotoCapabilities();
    })
    .then(photoCapabilities => {
      const settings = imageCapture.track.getSettings();

      input.min = photoCapabilities.imageWidth.min;
      input.max = photoCapabilities.imageWidth.max;
      input.step = photoCapabilities.imageWidth.step;

      return imageCapture.getPhotoSettings();
    })
    .then(photoSettings => {
      input.value = photoSettings.imageWidth;
    })
    .catch(error => console.log('Argh!', error.name || error));

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-image/#dom-imagecapture-getphotosettings">MediaStream Image Capture<br />
<span class="small">The definition of 'getPhotoSettings()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getPhotoSettings`

61

≤79

No

See [bug 888177](https://bugzil.la/888177).

No

46

No

61

61

No

See [bug 888177](https://bugzil.la/888177).

43

No

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageCapture/getPhotoSettings" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageCapture/getPhotoSettings</a>
