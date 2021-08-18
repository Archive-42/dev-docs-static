MediaStream Image Capture API
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The **MediaStream Image Capture API** is an API for capturing images or videos from a photographic device. In addition to capturing data, it also allows you to retrieve information about device capabilities such as image size, red-eye reduction and whether or not there is a flash and what they are currently set to. Conversely, the API allows the capabilities to be configured within the constraints what the device allows.

MediaStream image capture concepts and usage
--------------------------------------------

The process of retrieving an image or video stream happens as described below. The example code is adapted from [Chrome's Image Capture examples](https://googlechrome.github.io/samples/image-capture/).

First, get a reference to a device by calling [`MediaDevices.getUserMedia()`](mediadevices/getusermedia). The example below says give me whatever video device is available, though the `getUserMedia()` method allows more specific capabilities to be requested. This method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`MediaStream`](mediastream) object.

    navigator.mediaDevices.getUserMedia({ video: true })
      .then(mediaStream => {
        // Do something with the stream.
      })

Next, isolate the visual part of the media stream. Do this by calling [`MediaStream.getVideoTracks()`](mediastream/getvideotracks). This returns an array of [`MediaStreamTrack`](mediastreamtrack) objects. The code below assumes that the first item in the `MediaStreamTrack` array is the one to use. You can use the properties of the `MediaStreamTrack` objects to select the one you need.

    const track = mediaStream.getVideoTracks()[0];

At this point, you might want to configure the device capabilities before capturing an image. You can do this by calling [`applyConstraints()`](mediastreamtrack/applyconstraints) on the track object before doing anything else.

    let zoom = document.querySelector('#zoom');
    const capabilities = track.getCapabilities();
    // Check whether zoom is supported or not.
    if(!capabilities.zoom) {
      return;
    }
    track.applyConstraints({ advanced : [{ zoom: zoom.value }] });

Finally, pass the `MediaStreamTrack` object to the [`ImageCapture()`](imagecapture/imagecapture) constructor. Though a `MediaStream` holds several types of tracks and provides multiple methods for retrieving them, the ImageCapture constructor will throw a [`DOMException`](domexception) of type `NotSupportedError` if [`MediaStreamTrack.kind`](mediastreamtrack/kind) is not `"video"`.

    let imageCapture = new ImageCapture(track);

Interfaces
----------

[`ImageCapture`](imagecapture)  
An interface for capturing images from a photographic device referenced through a valid [`MediaStreamTrack`](mediastreamtrack).

[`PhotoCapabilities`](photocapabilities)  
Provides available configuration options for an attached photographic device. Retrieve a `PhotoCapabilities` object by calling [`ImageCapture.getPhotoCapabilities()`](imagecapture/getphotocapabilities).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-image/">MediaStream Image Capture</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MediaStream_Image_Capture_API`

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

`MediaStream_Image_Capture_API`

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

BCD tables only load in the browser

### PhotoCapabilities

BCD tables only load in the browser

See also
--------

-   [`MediaStream`](mediastream)
-   [`MediaStreamTrack`](mediastreamtrack)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Image_Capture_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Image_Capture_API</a>
