ImageCapture.getPhotoCapabilities()
===================================

The `getPhotoCapabilities()` method of the [`ImageCapture`](../imagecapture) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`PhotoCapabilities`](../photocapabilities) object containing the ranges of available configuration options.

Syntax
------

    const capabilitiesPromise = imageCaptureObj.getPhotoCapabilities()

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`PhotoCapabilities`](../photocapabilities) object.

Example
-------

The following example, extracted from [Chrome's Image Capture / Photo Resolution Sample](https://googlechrome.github.io/samples/image-capture/photo-resolution.html), uses the results from `getPhotoCapabilities()` to modify the size of an input range. This example also shows how the [`ImageCapture`](../imagecapture) object is created using a [`MediaStreamTrack`](../mediastreamtrack) retrieved from a device's [`MediaStream`](../mediastream).

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-image/#dom-imagecapture-getphotocapabilities">MediaStream Image Capture<br />
<span class="small">The definition of 'getPhotoCapabilities()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getPhotoCapabilities`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageCapture/getPhotoCapabilities" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageCapture/getPhotoCapabilities</a>
