VRPose.angularAcceleration
==========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `angularAcceleration` read-only property of the [`VRPose`](../vrpose) interface returns an array representing the angular acceleration vector of the [`VRDisplay`](../vrdisplay) at the current [`VRPose.timestamp`](timestamp), in meters per second per second.

In other words, the current acceleration of the sensor's rotation around the `x`, `y`, and `z` axes.

Syntax
------

    var myAngularAcceleration = VRPose.angularAcceleration;

### Value

A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array), or `null` if the VR sensor is not able to provide angular acceleration information.

Examples
--------

    // rendering loop for a VR scene
    function drawVRScene() {
      // WebVR: Request the next frame of the animation
      vrSceneFrame = vrDisplay.requestAnimationFrame(drawVRScene);

      // Populate frameData with the data of the next frame to display
      vrDisplay.getFrameData(frameData);

      // Retrieve the angular acceleration values for use in rendering
      // curFramePose is a VRPose object
      var curFramePose = frameData.pose;
      var angAcc = curFramePose.angularAcceleration;
      var aax = angAcc[0];
      var aay = angAcc[1];
      var aaz = angAcc[2];

      // render the scene
      ...

      // WebVR: submit the rendered frame to the VR display
      vrDisplay.submitFrame();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vrpose-angularacceleration">WebVR 1.1<br />
<span class="small">The definition of 'angularAcceleration' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`angularAcceleration`

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

-   [WebVR API homepage](../webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRPose/angularAcceleration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRPose/angularAcceleration</a>
