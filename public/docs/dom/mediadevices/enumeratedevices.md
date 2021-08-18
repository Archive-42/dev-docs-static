MediaDevices.enumerateDevices()
===============================

The [`MediaDevices`](../mediadevices) method `enumerateDevices()` requests a list of the available media input and output devices, such as microphones, cameras, headsets, and so forth. The returned [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is resolved with a [`MediaDeviceInfo`](../mediadeviceinfo) array describing the devices.

Syntax
------

    var enumeratorPromise = navigator.mediaDevices.enumerateDevices();

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that receives an array of [`MediaDeviceInfo`](../mediadeviceinfo) objects when the promise is fulfilled. Each object in the array describes one of the available media input and output devices. The order is significant - the default capture devices will be listed first.

If enumeration fails, the promise is rejected.

Example
-------

Here's an example of using `enumerateDevices()`. It outputs a list of the [device IDs](../mediadeviceinfo/deviceid), with their labels if available.

    if (!navigator.mediaDevices || !navigator.mediaDevices.enumerateDevices) {
      console.log("enumerateDevices() not supported.");
      return;
    }

    // List cameras and microphones.

    navigator.mediaDevices.enumerateDevices()
    .then(function(devices) {
      devices.forEach(function(device) {
        console.log(device.kind + ": " + device.label +
                    " id = " + device.deviceId);
      });
    })
    .catch(function(err) {
      console.log(err.name + ": " + err.message);
    });

This might produce:

    videoinput: id = csO9c0YpAf274OuCPUA53CNE0YHlIr2yXCi+SqfBZZ8=
    audioinput: id = RKxXByjnabbADGQNNZqLVLdmXlS0YkETYCIbg+XxnvM=
    audioinput: id = r2/xw1xUPIyZunfV1lGrKOma5wTOvCkWfZ368XCndm0=

or if one or more [`MediaStream`](../mediastream)s are active or persistent permissions are granted:

    videoinput: FaceTime HD Camera (Built-in) id=csO9c0YpAf274OuCPUA53CNE0YHlIr2yXCi+SqfBZZ8=
    audioinput: default (Built-in Microphone) id=RKxXByjnabbADGQNNZqLVLdmXlS0YkETYCIbg+XxnvM=
    audioinput: Built-in Microphone id=r2/xw1xUPIyZunfV1lGrKOma5wTOvCkWfZ368XCndm0=

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediadevices-enumeratedevices">Media Capture and Streams<br />
<span class="small">The definition of 'mediaDevices: enumerateDevices' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`enumerateDevices`

47

12

39

63

Prior to Firefox 63, `enumerateDevices()` only returned input devices. Starting with Firefox 63, output devices are also included if the `media.setsinkid.enabled` preference is enabled.

No

34

11

47

47

39

63

Prior to Firefox 63, `enumerateDevices()` only returned input devices. Starting with Firefox 63, output devices are also included if the `media.setsinkid.enabled` preference is enabled.

34

11

5.0

See also
--------

-   [`MediaDevices.getUserMedia`](getusermedia)
-   [WebRTC](../webrtc_api) - the introductory page to the API
-   [MediaStream API](../media_streams_api) - the API for the media stream objects
-   [Taking webcam photos](../webrtc_api/taking_still_photos) - a tutorial on using `getUserMedia()` for taking photos rather than video.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/enumerateDevices" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/enumerateDevices</a>
