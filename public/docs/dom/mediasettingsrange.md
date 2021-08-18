MediaSettingsRange
==================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `MediaSettingsRange` interface of the [MediaStream Image Capture API](mediastream_image_capture_api) provides the possible range and value size of [`PhotoCapabilities.imageHeight`](photocapabilities/imageheight) and [`PhotoCapabilities.imageWidth`](photocapabilities/imagewidth). A [`PhotoCapabilities`](photocapabilities) object can be retrieved by calling <span class="page-not-created">`ImageCapture.PhotoCapabilities()`</span>.

Properties
----------

[`MediaSettingsRange.max`](mediasettingsrange/max)  
Returns the maximum value of this settings.

[`MediaSettingsRange.min`](mediasettingsrange/min)  
Returns the minimum value of this setting.

[`MediaSettingsRange.step`](mediasettingsrange/step)  
Returns the minimum difference between consecutive values of this setting.

Example
-------

The following example, extracted from [Chrome's Image Capture / Photo Resolution Sample](https://googlechrome.github.io/samples/image-capture/photo-resolution.html), uses the results from `getPhotoCapabilities().imageWidth` to modify the size of an input range.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-image/#mediasettingsrange-section">MediaStream Image Capture<br />
<span class="small">The definition of 'MediaSettingsRange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MediaSettingsRange`

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

`max`

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

`min`

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

`step`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSettingsRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSettingsRange</a>
