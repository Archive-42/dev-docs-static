PhotoCapabilities
=================

The `PhotoCapabilities` interface of the [MediaStream Image Capture API](mediastream_image_capture_api) provides available configuration options for an attached photographic device. A `PhotoCapabilities` object is retrieved by calling [`ImageCapture.getPhotoCapabilities()`](imagecapture/getphotocapabilities).

Properties
----------

 [`PhotoCapabilities.redEyeReduction`](photocapabilities/redeyereduction) <span class="badge inline readonly">Read only </span>   
Returns one of `"never"`, `"always"`, or `"controllable"`. The `"controllable"` value means the device's red-eye reduction is controllable by the user.

 [`PhotoCapabilities.imageHeight`](photocapabilities/imageheight) <span class="badge inline readonly">Read only </span>   
Returns a [`MediaSettingsRange`](mediasettingsrange) object indicating the image height range supported by the user agent.

 [`PhotoCapabilities.imageWidth`](photocapabilities/imagewidth) <span class="badge inline readonly">Read only </span>   
Returns a [`MediaSettingsRange`](mediasettingsrange) object indicating the image width range supported by the user agent.

 [`PhotoCapabilities.fillLightMode`](photocapabilities/filllightmode) <span class="badge inline readonly">Read only </span>   
Returns an array of available fill light options. Options may include `auto`, `off`, or `flash`.

Example
-------

The following example, extracted from [Chrome's Image Capture / Photo Resolution Sample](https://googlechrome.github.io/samples/image-capture/photo-resolution.html), uses the results from [`getPhotoCapabilities()`](imagecapture/getphotocapabilities) to modify the size of an input range. This example also shows how the [`ImageCapture`](imagecapture) object is created using a [`MediaStreamTrack`](mediastreamtrack) retrieved from a device's [`MediaStream`](mediastream).

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-image/#photocapabilities-section">MediaStream Image Capture<br />
<span class="small">The definition of 'PhotoCapabilities' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PhotoCapabilities`

59

≤79

?

No

46

No

59

59

?

43

No

7.0

`fillLightMode`

59

≤79

?

No

46

No

59

59

?

43

No

7.0

`imageHeight`

59

≤79

?

No

46

No

59

59

?

43

No

7.0

`imageWidth`

59

≤79

?

No

46

No

59

59

?

43

No

7.0

`redEyeReduction`

59

≤79

?

No

46

No

59

59

?

43

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PhotoCapabilities" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PhotoCapabilities</a>
