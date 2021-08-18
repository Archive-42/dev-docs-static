MediaDeviceInfo.groupId
=======================

The `groupId` readonly property of the [`MediaDeviceInfo`](../mediadeviceinfo) interface returns a [`DOMString`](../domstring) that is a group identifier. Two devices have the same group identifier if they belong to the same physical device; for example, a monitor with both a built-in camera and microphone.

Syntax
------

    var groupID = mediaDeviceInfo.groupId;

### Value

A [`DOMString`](../domstring) which uniquely identifies the group of related devices to which this device belongs.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediadeviceinfo-groupid">Media Capture and Streams<br />
<span class="small">The definition of 'groupId' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Examples
--------

In this example, we assemble a list of the devices which are part of the same group as a given device. This might be used to produce a user interface that gathers associated devices together for presentation purposes, or to make it easy for the user to choose to use the built-in camera and microphone on the same display at the same time.

    const getDeviceGroup = mainDevInfo => {
      let devList = [];

      navigator.mediaDevices.enumerateDevices()
      .then(devices => {
        devices.forEach(device => {
          if (device.groupId === mainDevInfo.groupId) {
            devList.push(device);
          }
        });
      });

      return devList;
    };

The `getDeviceGroup()` function takes as input the `MediaDeviceInfo` object describing the device for which a group list is to be built. The function starts by initializing the result array, `devList`, to be an empty array.

Then [`navigator.mediaDevices.enumerateDevices()`](../mediadevices/enumeratedevices) is called to get the list of all media devices. Once the promise resolves, we walk the list using [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach). For each device, if its [`groupId`](groupid) matches the main device's `groupId`, we push the [`MediaDeviceInfo`](../mediadeviceinfo) object onto the list.

Finally, the list, which now contains a `MediaDeviceInfo` object for each device in the same group, is returned to the caller.

This could be altered easily to either leave out the passed-in device from the returned list, or to place it at the top of the list, by comparing the two objects' [`deviceId`](deviceid) values, only pushing the device onto the result list if it doesn't match.

This version of the example puts the passed-in device at the top of the result list, then adds any other members of the group that are found:

    const getDeviceGroup = mainDevInfo => {
      let devList = [mainDevInfo];

      navigator.mediaDevices.enumerateDevices()
      .then(devices => {
        devices.forEach(device => {
          if ((device.groupId === mainDevInfo.groupId) &&
              (device.deviceId !== mainDevInfo.deviceId)) {
            devList.push(device);
          }
        });
      });

      return devList;
    };

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaDeviceInfo/groupId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaDeviceInfo/groupId</a>
