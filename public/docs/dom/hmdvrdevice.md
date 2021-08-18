HMDVRDevice
===========

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `HMDVRDevice` interface of the [WebVR API](webvr_api) represents a head mounted display, providing access to information about each eye, and allowing us to modify the current field of view.

Methods
-------

[`HMDVRDevice.getEyeParameters()`](hmdvrdevice/geteyeparameters)  
Returns current parameters for the eye specified as its argument ("left" or "right") — such as field of view information — stored in a [`VREyeParameters`](vreyeparameters) object.

[`HMDVRDevice.setFieldOfView()`](hmdvrdevice/setfieldofview)  
Sets the field of view for both eyes.

Properties
----------

*This interface doesn't define any properties of its own, but it does inherit the properties of its parent interface, [`VRDevice`](vrdisplay).*

 [`VRDevice.hardwareUnitId`](vrdisplay/hardwareunitid) <span class="badge inline readonly">Read only </span>   
Returns the distinct hardware ID for the overall hardware unit that this `VRDevice` is a part of. All devices that are part of the same physical piece of hardware will have the same `hardwareUnitId`.

 [`VRDevice.deviceId`](vrdisplay/displayid) <span class="badge inline readonly">Read only </span>   
Returns the ID for this specific `VRDevice`. The ID shouldn’t change across browser restarts, allowing configuration data to be saved based on it.

 [`VRDevice.deviceName`](vrdisplay/displayname) <span class="badge inline readonly">Read only </span>   
A human-readable name to identify the `VRDevice`.

Examples
--------

The following example, taken from the WebVR spec, finds the first available `HMDVRDevice` and its associated [`PositionSensorVRDevice`](positionsensorvrdevice), if it has one.

    navigator.getVRDevices().then(function(devices) {
      for (var i = 0; i < devices.length; ++i) {
        if (devices[i] instanceof HMDVRDevice) {
          gHMD = devices[i];
          break;
        }
      }

      if (gHMD) {
        for (var i = 0; i < devices.length; ++i) {
          if (devices[i] instanceof PositionSensorVRDevice && devices[i].hardwareUnitId === gHMD.hardwareUnitId) {
            gPositionSensor = devices[i];
            break;
          }
        }
      }
    });

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

`HMDVRDevice`

No

No

39

The support for this feature is currently disabled by default in Firefox. To enable WebVR support in Firefox Nightly/Developer Edition, you can go to `about:config` and enable the `dom.vr*` prefs. A better option however is to install the [WebVR Enabler Add-on](http://www.mozvr.com/downloads/webvr-addon-0.1.0.xpi), which does this for you and sets up other necessary parts of the [environment](https://developer.mozilla.org/docs/Web/API/WebVR_API/WebVR_environment_setup)

No

No

No

No

62

The support in Chrome is currently experimental. To find information on Chrome's WebVR implementation status including supporting builds, check out [Bringing VR to Chrome](http://blog.tojicode.com/2014/07/bringing-vr-to-chrome.html) by Brandon Jones.

44

The `dom.vr*` prefs are enabled by default at this point, in Nightly/Aurora editions.

39-44

The support for this feature is currently disabled by default in Firefox. To enable WebVR support in Firefox Nightly/Developer Edition, you can go to `about:config` and enable the `dom.vr*` prefs. A better option however is to install the [WebVR Enabler Add-on](http://www.mozvr.com/downloads/webvr-addon-0.1.0.xpi), which does this for you and sets up other necessary parts of the [environment](https://developer.mozilla.org/docs/Web/API/WebVR_API/WebVR_environment_setup).

No

No

8.0

`getEyeParameters`

No

No

39

The support for this feature is currently disabled by default in Firefox. To enable WebVR support in Firefox Nightly/Developer Edition, you can go to `about:config` and enable the `dom.vr*` prefs. A better option however is to install the [WebVR Enabler Add-on](http://www.mozvr.com/downloads/webvr-addon-0.1.0.xpi), which does this for you and sets up other necessary parts of the [environment](https://developer.mozilla.org/docs/Web/API/WebVR_API/WebVR_environment_setup)

No

No

No

No

62

The support in Chrome is currently experimental. To find information on Chrome's WebVR implementation status including supporting builds, check out [Bringing VR to Chrome](http://blog.tojicode.com/2014/07/bringing-vr-to-chrome.html) by Brandon Jones.

44

The `dom.vr*` prefs are enabled by default at this point, in Nightly/Aurora editions.

39-44

The support for this feature is currently disabled by default in Firefox. To enable WebVR support in Firefox Nightly/Developer Edition, you can go to `about:config` and enable the `dom.vr*` prefs. A better option however is to install the [WebVR Enabler Add-on](http://www.mozvr.com/downloads/webvr-addon-0.1.0.xpi), which does this for you and sets up other necessary parts of the [environment](https://developer.mozilla.org/docs/Web/API/WebVR_API/WebVR_environment_setup).

No

No

8.0

`setFieldOfView`

No

No

39

The support for this feature is currently disabled by default in Firefox. To enable WebVR support in Firefox Nightly/Developer Edition, you can go to `about:config` and enable the `dom.vr*` prefs. A better option however is to install the [WebVR Enabler Add-on](http://www.mozvr.com/downloads/webvr-addon-0.1.0.xpi), which does this for you and sets up other necessary parts of the [environment](https://developer.mozilla.org/docs/Web/API/WebVR_API/WebVR_environment_setup)

No

No

No

No

62

The support in Chrome is currently experimental. To find information on Chrome's WebVR implementation status including supporting builds, check out [Bringing VR to Chrome](http://blog.tojicode.com/2014/07/bringing-vr-to-chrome.html) by Brandon Jones.

44

The `dom.vr*` prefs are enabled by default at this point, in Nightly/Aurora editions.

39-44

The support for this feature is currently disabled by default in Firefox. To enable WebVR support in Firefox Nightly/Developer Edition, you can go to `about:config` and enable the `dom.vr*` prefs. A better option however is to install the [WebVR Enabler Add-on](http://www.mozvr.com/downloads/webvr-addon-0.1.0.xpi), which does this for you and sets up other necessary parts of the [environment](https://developer.mozilla.org/docs/Web/API/WebVR_API/WebVR_environment_setup).

No

No

8.0

See also
--------

-   [WebVR API homepage](webvr_api).
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HMDVRDevice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HMDVRDevice</a>
