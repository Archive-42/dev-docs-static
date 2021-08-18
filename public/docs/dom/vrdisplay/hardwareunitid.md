VRDevice.hardwareUnitId
=======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `hardwareUnitId` read-only property of the [`VRDisplay`](../vrdisplay) interface returns the distinct hardware ID for the overall hardware unit that this `VRDevice` is a part of. All devices that are part of the same physical piece of hardware will have the same `hardwareUnitId`.

Syntax
------

    var hardwareID = VRDevice.hardwareUnitId;

### Value

A [`DOMString`](../domstring) containing the ID of the overall hardware unit.

Examples
--------

The following snippet (see our [VRDevice example](https://mdn.github.io/webvr-tests/vrdevice/)) returns an array of all the [`VRDisplay`](../vrdisplay)s connected to your computer via [`Navigator.getVRDisplays`](../navigator/getvrdisplays). For each connected device it then prints out the `hardwareUnitId`, [`VRDisplay.displayId`](displayid), and [`VRDisplay.displayName`](displayname).

    var list = document.querySelector('ul');
    var info = document.querySelector('p');
    if(navigator.getVRDevices) {
      navigator.getVRDevices().then(function(myDevices) {
        reportDevices(myDevices);
      });
    } else {
      info.textContent = 'WebVR API not supported by this browser.'
    }

    function reportDevices(devices) {
      for(i = 0; i < devices.length; i++) {
        var listItem = document.createElement('li');
        listItem.innerHTML = 'Device ' + (i+1)
                     + ': <strong>Hardware ID</strong>: ' + devices[i].hardwareUnitId
                     + ', <strong>VD Device ID</strong>: ' + devices[i].deviceId
                     + ', <strong>VR Device Name</strong>: ' + devices[i].deviceName
                     + '.';
        list.appendChild(listItem);
      }
    }

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

`hardwareUnitId`

No

No

No

No

?

No

No

No

?

?

?

No

See also
--------

-   [WebVR API homepage](../webvr_api).
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/hardwareUnitId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/hardwareUnitId</a>
