ImageCapture.takePhoto()
========================

The `takePhoto()` method of the [`ImageCapture`](../imagecapture) interface takes a single exposure using the video capture device sourcing a [`MediaStreamTrack`](../mediastreamtrack) and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`Blob`](../blob) containing the data.

Syntax
------

    const blobPromise = imageCaptureObj.takePhoto()
    const blobPromise = imageCaptureObj.takePhoto(photoSettings)

### Parameters

 `photoSettings` <span class="badge inline optional">Optional</span>   
An object that sets options for the photo to be taken. The available options are:

-   `fillLightMode`: The flash setting of the capture device, one of `"auto"`, `"off"`, or `"flash"`.
-   `imageHeight`: The desired image height as an integer. The user agent selects the closest height value to this setting if it only supports discrete heights.
-   `imageWidth`: The desired image width as an integer. The user agent selects the closest width value to this setting if it only supports discrete widths.
-   `redEyeReduction`: A boolean indicating whether the red-eye reduction should be used if it is available.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`Blob`](../blob).

Example
-------

This example is extracted from this [Simple Image Capture demo](https://simpl.info/imagecapture/). It shows how to use the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by `takePhoto()` to copy the returned [`Blob`](../blob) to an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element. For simplicity it does not show how to instantiate the [`ImageCapture`](../imagecapture) object.

    var takePhotoButton = document.querySelector('button#takePhoto');
    var canvas = document.querySelector('canvas');

    takePhotoButton.onclick = takePhoto;

    function takePhoto() {
      imageCapture.takePhoto().then(function(blob) {
        console.log('Took photo:', blob);
        img.classList.remove('hidden');
        img.src = URL.createObjectURL(blob);
      }).catch(function(error) {
        console.log('takePhoto() error: ', error);
      });
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-image/#dom-imagecapture-takephoto">MediaStream Image Capture<br />
<span class="small">The definition of 'takePhoto()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`takePhoto`

60

59-60

`photoSettings` argument not supported.

≤79

No

See [bug 888177](https://bugzil.la/888177).

No

47

46-47

`photoSettings` argument not supported.

No

60

59-60

`photoSettings` argument not supported.

60

59-60

`photoSettings` argument not supported.

No

See [bug 888177](https://bugzil.la/888177).

44

43-44

`photoSettings` argument not supported.

No

8.0

7.0-8.0

`photoSettings` argument not supported.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageCapture/takePhoto" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageCapture/takePhoto</a>
