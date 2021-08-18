HMDVRDevice.setFieldOfView()
============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `setFieldOfView()` method of the [`HMDVRDevice`](../hmdvrdevice) interface can be used to set the field of view for one eye, or both eyes simultaneously.

Syntax
------

    HMDVRDevice.setFieldOfView(leftFOV,rightFOV,zNear,zFar);

### Parameters

`leftFOV Optional`  
A `VRFieldOfView` object that defines the new field of view for the left eye. If not specified, the left eye field of view does not change.

`rightFOV Optional`  
A `VRFieldOfView` object that defines the new field of view for the right eye. If not specified, the right eye field of view does not change.

`zNear Optional`  
The distance from the eyes of the nearest point of the view. The closest things can be and still be in the view. If not specified, the default is used — `0.01`.

`zFar Optional`  
The distance from the eyes of the farthest point of the view. The furthest away things can be and still be in the view. If not specified, the default is used — `10000.0`.

### Returns

Void.

Examples
--------

The following simple example shows a function that can be used to set a custom field of view with four specified degree values for up, right, down and left. The [`VRFieldOfView()`](../vrfieldofview/vrfieldofview) constructor is used to create a [`VRFieldOfView`](../vrfieldofview) object from the supplied values, which is then fed into the `setFieldOfView()` method (the default `zNear` and `zFar` values are always used, in this case.)

    function setCustomFOV(up,right,down,left) {
      var testFOV = new VRFieldOfView(up,right,down,left);

      gHMD.setFieldOfView(testFOV,testFOV,0.01,10000.0);

      var lEye = gHMD.getEyeParameters('left');
      var rEye = gHMD.getEyeParameters('right');
      console.log(lEye.currentFieldOfView);
      console.log(rEye.currentFieldOfView);
    }

**Note**: When testing, setting a weird/tiny field of view can really mess up your view. It is a good idea to grab the current field of view first (using [`VREyeParameters.currentFieldOfView`](../vreyeparameters/fieldofview)) before making any drastic changes, so you can reset it afterwards if needed.

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

-   [WebVR API homepage](../webvr_api).
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HMDVRDevice/setFieldOfView" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HMDVRDevice/setFieldOfView</a>
