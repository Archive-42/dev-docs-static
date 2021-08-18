MediaDeviceInfo
===============

The `MediaDeviceInfo` interface contains information that describes a single media input or output device. The list of devices obtained by calling [`navigator.mediaDevices.enumerateDevices()`](mediadevices/enumeratedevices) is an array of `MediaDeviceInfo` objects, one per media device.

Properties
----------

 [`MediaDeviceInfo.deviceId`](mediadeviceinfo/deviceid)<span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) that is an identifier for the represented device that is persisted across sessions. It is un-guessable by other applications and unique to the origin of the calling application. It is reset when the user clears cookies (for Private Browsing, a different identifier is used that is not persisted across sessions).

 [`MediaDeviceInfo.groupId`](mediadeviceinfo/groupid)<span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) that is a group identifier. Two devices have the same group identifier if they belong to the same physical device — for example a monitor with both a built-in camera and a microphone.

 [`MediaDeviceInfo.kind`](mediadeviceinfo/kind)<span class="badge inline readonly">Read only </span>   
Returns an enumerated value that is either `"videoinput"`, `"audioinput"` or `"audiooutput"`.

 [`MediaDeviceInfo.label`](mediadeviceinfo/label)<span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) that is a label describing this device (for example "External USB Webcam").

For security reasons, the `label` field is always blank unless an active media stream exists *or* the user has granted persistent permission for media device access. The set of device labels could otherwise be used as part of a fingerprinting mechanism to identify a user.

Methods
-------

None.

Example
-------

Here's an example that uses [`enumerateDevices()`](mediadevices/enumeratedevices) to get a list of devices.

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

or if one or more media streams are active, or if persistent permissions have been granted:

    videoinput: FaceTime HD Camera (Built-in) id=csO9c0YpAf274OuCPUA53CNE0YHlIr2yXCi+SqfBZZ8=
    audioinput: default (Built-in Microphone) id=RKxXByjnabbADGQNNZqLVLdmXlS0YkETYCIbg+XxnvM=
    audioinput: Built-in Microphone id=r2/xw1xUPIyZunfV1lGrKOma5wTOvCkWfZ368XCndm0=

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediadeviceinfo">Media Capture and Streams<br />
<span class="small">The definition of 'MediaDevicesInfo' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`MediaDeviceInfo`

55

12

39

No

42

11

55

55

39

42

11

6.0

`deviceId`

55

12

39

No

42

11

55

55

39

42

11

6.0

`groupId`

55

12

39

Prior to Firefox 67, related devices are not actually grouped together by `groupId`.

No

42

11

55

55

39

Prior to Firefox 67, related devices are not actually grouped together by `groupId`.

42

11

6.0

`kind`

55

12

39

No

42

11

55

55

39

42

11

6.0

`label`

55

12

39

No

42

11

55

55

39

42

11

6.0

`toJSON`

55

18

42

No

42

11

55

55

42

42

11

6.0

See also
--------

-   [WebRTC API](webrtc_api)
-   [`navigator.mediaDevices.enumerateDevices()`](mediadevices/enumeratedevices)
-   [`navigator.mediaDevices.getUserMedia()`](mediadevices/getusermedia)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaDeviceInfo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaDeviceInfo</a>
