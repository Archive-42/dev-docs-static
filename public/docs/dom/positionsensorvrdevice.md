# PositionSensorVRDevice

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PositionSensorVRDevice` interface of the [WebVR API](webvr_api) represents VR hardware's position sensor. You can access information such as the current position and orientation of the sensor in relation to the head mounted display through the [`PositionSensorVRDevice.getState()`](positionsensorvrdevice/getstate) method.

## Methods

[`PositionSensorVRDevice.getState()`](positionsensorvrdevice/getstate)  
Returns the current state of the position sensor for the current frame (e.g. within the current [`window.requestAnimationFrame`](window/requestanimationframe) callback) or for the previous frame, contained with a [`VRPose`](vrpose) object. This is the method you'd normally want to use, versus `getImmediateState()`.

[`PositionSensorVRDevice.getImmediateState()`](positionsensorvrdevice/getimmediatestate)  
Returns the current instantaneous position sensor state. This is intended to only be used rarely, for certain special uses, for example sampling the immediate position of a hand orientation sensor — or at least it will be, in the future.

[`PositionSensorVRDevice.resetSensor()`](positionsensorvrdevice/resetsensor)  
Can be used to reset the sensor if desired, returning the position and orientation values to zero.

## Properties

_This interface doesn't define any properties of its own, but it does inherit the properties of its parent interface, [`VRDisplay`](vrdisplay)._

[`VRDisplay.hardwareUnitId`](vrdisplay/hardwareunitid) <span class="badge inline readonly">Read only </span>  
Returns the distinct hardware ID for the overall hardware unit that this `VRDevice` is a part of. All devices that are part of the same physical piece of hardware will have the same `hardwareUnitId`.

[`VRDisplay.displayId`](vrdisplay/displayid) <span class="badge inline readonly">Read only </span>  
Returns the ID for this specific `VRDevice`. The ID shouldn’t change across browser restarts, allowing configuration data to be saved based on it.

[`VRDisplay.displayName`](vrdisplay/displayname) <span class="badge inline readonly">Read only </span>  
A human-readable name to identify the `VRDevice`.

## Examples

The following example is taken from our [positionsensorvrdevice](https://mdn.github.io/webvr-tests/positionsensorvrdevice/) demo, which uses the WebVR API to update the view of a simple [`2D canvas`](canvasrenderingcontext2d) scene on each frame of a [`requestAnimationFrame`](window/requestanimationframe) loop.

    function setView() {
      var posState = gPositionSensor.getState();
      if(posState.hasPosition) {
        posPara.textContent = 'Position: x' + roundToTwo(posState.position.x) + " y"
                                    + roundToTwo(posState.position.y) + " z"
                                    + roundToTwo(posState.position.z);
        xPos = -posState.position.x * WIDTH * 2;
        yPos = posState.position.y * HEIGHT * 2;
        if(-posState.position.z > 0.01) {
          zPos = -posState.position.z;
        } else {
          zPos = 0.01;
        }
      }

      if(posState.hasOrientation) {
        orientPara.textContent = 'Orientation: x' + roundToTwo(posState.orientation.x) + " y"
                                    + roundToTwo(posState.orientation.y) + " z"
                                    + roundToTwo(posState.orientation.z);
        xOrient = posState.orientation.x * WIDTH;
        yOrient = -posState.orientation.y * HEIGHT * 2;
        zOrient = posState.orientation.z * 180;

      }
    }

Here we are grabbing a [`VRPose`](vrpose) object using [`PositionSensorVRDevice.getState()`](positionsensorvrdevice/getstate) and storing it in `posState`. We then check to make sure that position and orientation info is present in the current frame using [`VRPose.hasPosition`](vrpose/hasposition) and [`VRPose.hasOrientation`](vrpose/hasorientation) (these return `null` if, for example the head mounted display is turned off or not pointing at the position sensor, which would cause an error.)

We then output the x, y and z position and orientation values for informational purposes, and use those values to update the `xPos`, `yPos`, ` zPos, ``xOrient `, `yOrient`, and `zOrient` variables, which are used to update the scene rendering on each frame.

## Browser compatibility

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

`PositionSensorVRDevice`

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

`getImmediateState`

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

`getState`

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

## See also

- [WebVR API homepage](webvr_api).
- <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PositionSensorVRDevice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PositionSensorVRDevice</a>
