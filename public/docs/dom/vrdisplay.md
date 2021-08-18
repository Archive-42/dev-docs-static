VRDisplay
=========

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `VRDisplay` interface of the [WebVR API](webvr_api) represents any VR device supported by this API. It includes generic information such as device IDs and descriptions, as well as methods for starting to present a VR scene, retrieving eye parameters and display capabilities, and other important functionality.

An array of all connected VR Devices can be returned by invoking the [`Navigator.getVRDisplays()`](navigator/getvrdisplays) method.

Properties
----------

 [`VRDisplay.capabilities`](vrdisplay/capabilities) <span class="badge inline readonly">Read only </span>   
Returns a [`VRDisplayCapabilities`](vrdisplaycapabilities) object that indicates the various capabilities of the `VRDisplay`.

[`VRDisplay.depthFar`](vrdisplay/depthfar)  
Gets and sets the z-depth defining the far plane of the [eye view frustum](https://en.wikipedia.org/wiki/Viewing_frustum), i.e. the furthest viewable boundary of the scene.

[`VRDisplay.depthNear`](vrdisplay/depthnear)  
Gets and sets the z-depth defining the near plane of the [eye view frustum](https://en.wikipedia.org/wiki/Viewing_frustum), i.e. the nearest viewable boundary of the scene.

 [`VRDisplay.displayId`](vrdisplay/displayid) <span class="badge inline readonly">Read only </span>   
Returns an identifier for this particular VRDisplay, which is also used as an association point in the [Gamepad API](gamepad_api) (see [`Gamepad.displayId`](gamepad/displayid)).

 [`VRDisplay.displayName`](vrdisplay/displayname) <span class="badge inline readonly">Read only </span>   
Returns a human-readable name to identify the `VRDisplay`.

 [`VRDisplay.isConnected`](vrdisplay/isconnected) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the `VRDisplay` is connected to the computer.

 [`VRDisplay.isPresenting`](vrdisplay/ispresenting) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the `VRDisplay` is currently having content presented through it.

 [`VRDisplay.stageParameters`](vrdisplay/stageparameters) <span class="badge inline readonly">Read only </span>   
Returns a [`VRStageParameters`](vrstageparameters) object containing room-scale parameters, if the `VRDisplay` is capable of supporting room-scale experiences.

Methods
-------

[`VRDisplay.getEyeParameters()`](vrdisplay/geteyeparameters)  
Returns the [`VREyeParameters`](vreyeparameters) object containing the eye parameters for the specified eye.

[`VRDisplay.getFrameData()`](vrdisplay/getframedata)  
Accepts a [`VRFrameData`](vrframedata) object and populates it with the information required to render the current frame.

[`VRDisplay.getLayers()`](vrdisplay/getlayers)  
Returns the layers currently being presented by the `VRDisplay`.

[`VRDisplay.resetPose()`](vrdisplay/resetpose)  
Resets the pose for this `VRDisplay`, treating its current [`VRPose.position`](vrpose/position) and [`VRPose.orientation`](vrpose/orientation) as the "origin/zero" values.

[`VRDisplay.cancelAnimationFrame()`](vrdisplay/cancelanimationframe)  
A special implementation of [`Window.cancelAnimationFrame`](window/cancelanimationframe) that allows callbacks registered with [`VRDisplay.requestAnimationFrame()`](vrdisplay/requestanimationframe) to be unregistered.

[`VRDisplay.requestAnimationFrame()`](vrdisplay/requestanimationframe)  
A special implementation of [`Window.requestAnimationFrame`](window/requestanimationframe) containing a callback function that will be called every time a new frame of the `VRDisplay` presentation is rendered.

[`VRDisplay.requestPresent()`](vrdisplay/requestpresent)  
Starts the `VRDisplay` presenting a scene.

[`VRDisplay.exitPresent()`](vrdisplay/exitpresent)  
Stops the `VRDisplay` presenting a scene.

[`VRDisplay.submitFrame()`](vrdisplay/submitframe)  
Captures the current state of the [`VRLayerInit`](vrlayerinit) currently being presented and displays it on the `VRDisplay`.

### Deprecated methods

 [`VRDisplay.getPose()`](vrdisplay/getpose) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns a [`VRPose`](vrpose) object defining the future predicted pose of the `VRDisplay` as it will be when the current frame is actually presented. **This method is deprecated — instead, you should use [`VRDisplay.getFrameData()`](vrdisplay/getframedata), which also provides a [`VRPose`](vrpose) object.**

### Obsolete methods

 [`VRDisplay.getImmediatePose()`](vrdisplay/getimmediatepose) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns a [`VRPose`](vrpose) object defining the current pose of the `VRDisplay`, with no prediction applied. This is no longer needed, and has been removed from the spec.

 [`VRDisplay.hardwareUnitId`](vrdisplay/hardwareunitid) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns a [`DOMString`](domstring) defining the shared ID of the display, and any other devices that are part of that hardware set (e.g. controllers). This is no longer needed, and has been removed from the spec. Displays now use [`VRDisplay.displayId`](vrdisplay/displayid), and corresponsing controllers will now return the same ID under [`Gamepad.displayId`](gamepad/displayid).

Examples
--------

    if(navigator.getVRDisplays) {
      console.log('WebVR 1.1 supported');
      // Then get the displays attached to the computer
      navigator.getVRDisplays().then(function(displays) {
        // If a display is available, use it to present the scene
        if(displays.length > 0) {
          vrDisplay = displays[0];
          // Now we have our VRDisplay object and can do what we want with it
        }
      });
    }

**Note**: You can see this complete code at [raw-webgl-example](https://github.com/mdn/webvr-tests/blob/master/raw-webgl-example/webgl-demo.js).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#interface-vrdisplay">WebVR 1.1<br />
<span class="small">The definition of 'VRDisplay' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`VRDisplay`

No

≤18-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`cancelAnimationFrame`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`capabilities`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`depthFar`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`depthNear`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`displayId`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`displayName`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`exitPresent`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`getEyeParameters`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`getFrameData`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`getImmediatePose`

No

No

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

No

55

?

?

No

`getLayers`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`getPose`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

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

`isConnected`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`isPresenting`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`requestAnimationFrame`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`requestPresent`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`resetPose`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`stageParameters`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

`submitFrame`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

See also
--------

-   [WebVR API homepage](webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay</a>
