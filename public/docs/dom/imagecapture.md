ImageCapture
============

The `ImageCapture` interface of the [MediaStream Image Capture API](mediastream_image_capture_api) provides methods to enable the capture of images or photos from a camera or other photographic device. It provides an interface for capturing images from a photographic device referenced through a valid [`MediaStreamTrack`](mediastreamtrack).

Constructor
-----------

[`ImageCapture()`](imagecapture/imagecapture)  
Creates a new `ImageCapture` object which can be used to capture still frames (photos) from a given [`MediaStreamTrack`](mediastreamtrack) which represents a video stream.

Properties
----------

 [`ImageCapture.track`](imagecapture/track) <span class="badge inline readonly">Read only </span>   
Returns a reference to the [`MediaStreamTrack`](mediastreamtrack) passed to the constructor.

Methods
-------

The `ImageCapture` interface is based on [`EventTarget`](eventtarget), so it includes the methods defined by that interface as well as the ones listed below.

[`ImageCapture.takePhoto()`](imagecapture/takephoto)  
Takes a single exposure using the video capture device sourcing a [`MediaStreamTrack`](mediastreamtrack) and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`Blob`](blob) containing the data.

[`ImageCapture.getPhotoCapabilities()`](imagecapture/getphotocapabilities)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`PhotoCapabilities`](photocapabilities) object containing the ranges of available configuration options.

[`ImageCapture.getPhotoSettings()`](imagecapture/getphotosettings)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a <span class="page-not-created">`PhotoSettings`</span> object containing the current photo configuration settings.

[`ImageCapture.grabFrame()`](imagecapture/grabframe)  
Takes a snapshot of the live video in a [`MediaStreamTrack`](mediastreamtrack), returning an [`ImageBitmap`](imagebitmap), if successful.

Example
-------

The following code is taken from [Chrome's Grab Frame - Take Photo Sample](https://googlechrome.github.io/samples/image-capture/grab-frame-take-photo.html). Since `ImageCapture` requires some place to capture an image from, the example below starts with a device's media device (in other words a camera).

This example shows, roughly, a [`MediaStreamTrack`](mediastreamtrack) extracted from a device's [`MediaStream`](mediastream). The track is then used to create an `ImageCapture` object so that `takePhoto()` and `grabFrame()` can be called. Finally, it shows how to apply the results of these calls to a canvas object.

    var imageCapture;

    function onGetUserMediaButtonClick() {
      navigator.mediaDevices.getUserMedia({video: true})
      .then(mediaStream => {
        document.querySelector('video').srcObject = mediaStream;

        const track = mediaStream.getVideoTracks()[0];
        imageCapture = new ImageCapture(track);
      })
      .catch(error => console.log(error));
    }

    function onGrabFrameButtonClick() {
      imageCapture.grabFrame()
      .then(imageBitmap => {
        const canvas = document.querySelector('#grabFrameCanvas');
        drawCanvas(canvas, imageBitmap);
      })
      .catch(error => console.log(error));
    }

    function onTakePhotoButtonClick() {
      imageCapture.takePhoto()
      .then(blob => createImageBitmap(blob))
      .then(imageBitmap => {
        const canvas = document.querySelector('#takePhotoCanvas');
        drawCanvas(canvas, imageBitmap);
      })
      .catch(error => console.log(error));
    }

    /* Utils */

    function drawCanvas(canvas, img) {
      canvas.width = getComputedStyle(canvas).width.split('px')[0];
      canvas.height = getComputedStyle(canvas).height.split('px')[0];
      let ratio  = Math.min(canvas.width / img.width, canvas.height / img.height);
      let x = (canvas.width - img.width * ratio) / 2;
      let y = (canvas.height - img.height * ratio) / 2;
      canvas.getContext('2d').clearRect(0, 0, canvas.width, canvas.height);
      canvas.getContext('2d').drawImage(img, 0, 0, img.width, img.height,
          x, y, img.width * ratio, img.height * ratio);
    }

    document.querySelector('video').addEventListener('play', function() {
      document.querySelector('#grabFrameButton').disabled = false;
      document.querySelector('#takePhotoButton').disabled = false;
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-image/#imagecaptureapi">MediaStream Image Capture<br />
<span class="small">The definition of 'ImageCapture' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`grabFrame`

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

`track`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageCapture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageCapture</a>
