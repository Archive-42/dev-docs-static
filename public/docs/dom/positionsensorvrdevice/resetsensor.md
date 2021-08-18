PositionSensorVRDevice.resetSensor()
====================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `resetSensor()` method of the [`VRDisplay`](../vrdisplay) interface can be used to reset the sensor if desired, returning the position and orientation values to zero.

Syntax
------

    PositionSensorVRDevice.resetSensor();

### Parameters

None.

### Returns

Void.

Examples
--------

Our [positionsensorvrdevice](https://mdn.github.io/webvr-tests/positionsensorvrdevice/) demo uses the WebVR API to update the view of a simple [`2D canvas`](../canvasrenderingcontext2d) scene on each frame of a [`requestAnimationFrame`](../window/requestanimationframe) loop. It features, among other things, a "Reset Sensor" button in the UI, which when pressed runs the `resetSensor()` function on the position sensor. The JavaScript looks like this:

    document.querySelector('button').onclick = function() {
      gPositionSensor.resetSensor();
    }

When the button is pressed, the current position, orientation, etc. of the sensor/head mounted display is set to be 0 — this makes the method useful for calibration when an app is first loaded.

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

`resetSensor`

Yes

The support in Chrome is currently experimental. To find information on Chrome's WebVR implementation status including supporting builds, check out [Bringing VR to Chrome](http://blog.tojicode.com/2014/07/bringing-vr-to-chrome.html) by Brandon Jones.

79

The support in Edge is currently experimental. To find information on Edge's WebVR implementation status including supporting builds, check out [Bringing VR to Edge](http://blog.tojicode.com/2014/07/bringing-vr-to-chrome.html) by Brandon Jones.

39

The support for this feature is currently disabled by default in Firefox. To enable WebVR support in Firefox Nightly/Developer Edition, you can go to `about:config` and enable the `dom.vr*` prefs. A better option however is to install the [WebVR Enabler Add-on](http://www.mozvr.com/downloads/webvr-addon-0.1.0.xpi), which does this for you and sets up other necessary parts of the [environment](https://developer.mozilla.org/docs/Web/API/WebVR_API/WebVR_environment_setup)

No

No

No

No

No

39

The support for this feature is currently disabled by default in Firefox. To enable WebVR support in Firefox Nightly/Developer Edition, you can go to `about:config` and enable the `dom.vr*` prefs. A better option however is to install the [WebVR Enabler Add-on](http://www.mozvr.com/downloads/webvr-addon-0.1.0.xpi), which does this for you and sets up other necessary parts of the [environment](https://developer.mozilla.org/docs/Web/API/WebVR_API/WebVR_environment_setup).

44

The `dom.vr*` prefs are enabled by default at this point, in Nightly/Aurora editions.

No

No

No

See also
--------

-   [WebVR API homepage](../webvr_api).
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PositionSensorVRDevice/resetSensor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PositionSensorVRDevice/resetSensor</a>
