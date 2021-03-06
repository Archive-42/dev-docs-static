VRPose
======

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `VRPose` interface of the [WebVR API](webvr_api) represents the state of a VR sensor at a given timestamp (which includes orientation, position, velocity, and acceleration information.)

This interface is accessible through the [`VRDisplay.getPose()`](vrdisplay/getpose) and [`VRDisplay.getFrameData()`](vrdisplay/getframedata) methods. [`VRDisplay.getPose()`](vrdisplay/getpose) is deprecated.

Properties
----------

 [`VRPose.position`](vrpose/position) <span class="badge inline readonly">Read only </span>   
Returns the position of the [`VRDisplay`](vrdisplay) at the current [`VRPose.timestamp`](vrpose/timestamp) as a 3D vector

 [`VRPose.linearVelocity`](vrpose/linearvelocity) <span class="badge inline readonly">Read only </span>   
Returns the linear velocity of the [`VRDisplay`](vrdisplay) at the current [`VRPose.timestamp`](vrpose/timestamp), in meters per second.

 [`VRPose.linearAcceleration`](vrpose/linearacceleration) <span class="badge inline readonly">Read only </span>   
Returns the linear acceleration of the [`VRDisplay`](vrdisplay) at the current [`VRPose.timestamp`](vrpose/timestamp), in meters per second per second.

 [`VRPose.orientation`](vrpose/orientation) <span class="badge inline readonly">Read only </span>   
Returns the orientation of the sensor at the current [`VRPose.timestamp`](vrpose/timestamp), as a quarternion value.

 [`VRPose.angularVelocity`](vrpose/angularvelocity) <span class="badge inline readonly">Read only </span>   
Returns the angular velocity of the [`VRDisplay`](vrdisplay) at the current [`VRPose.timestamp`](vrpose/timestamp), in radians per second.

 [`VRPose.angularAcceleration`](vrpose/angularacceleration) <span class="badge inline readonly">Read only </span>   
Returns the angular acceleration of the [`VRDisplay`](vrdisplay) at the current [`VRPose.timestamp`](vrpose/timestamp), in meters per second per second.

### Obsolete properties

 [`VRPose.timeStamp`](vrpose/timestamp) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns the current time stamp of the system ??? a monotonically increasing value useful for determining if position data has been updated, and what order updates have occurred in. **This version of `timestamp` has been removed from the spec ??? instead, timestamps are now returned when [`VRDisplay.getFrameData()`](vrdisplay/getframedata) is called ??? see [`VRFrameData.timestamp`](vrframedata/timestamp).**

Examples
--------

    var frameData = new VRFrameData();
    var vrDisplay;

    navigator.getVRDisplays().then(function(displays) {
      vrDisplay = displays[0];
      console.log('Display found');
      // Starting the presentation when the button is clicked: It can only be called in response to a user gesture
      btn.addEventListener('click', function() {
        vrDisplay.requestPresent([{ source: canvas }]).then(function() {
          drawVRScene();
        });
      });
    });

    // WebVR: Draw the scene for the WebVR display.
    function drawVRScene() {
      // WebVR: Request the next frame of the animation
      vrSceneFrame = vrDisplay.requestAnimationFrame(drawVRScene);

      // Populate frameData with the data of the next frame to display
      vrDisplay.getFrameData(frameData);

      // You can get the position, orientation, etc. of the display from the current frame's pose
      // curFramePose is a VRPose object
      var curFramePose = frameData.pose;
      var curPos = curFramePose.position;
      var curOrient = curFramePose.orientation;

      // Clear the canvas before we start drawing on it.

      gl.clear(gl.COLOR_BUFFER_BIT | gl.DEPTH_BUFFER_BIT);

      // WebVR: Create the required projection and view matrix locations needed
      // for passing into the uniformMatrix4fv methods below

      var projectionMatrixLocation = gl.getUniformLocation(shaderProgram, "projMatrix");
      var viewMatrixLocation = gl.getUniformLocation(shaderProgram, "viewMatrix");

      // WebVR: Render the left eye???s view to the left half of the canvas
      gl.viewport(0, 0, canvas.width * 0.5, canvas.height);
      gl.uniformMatrix4fv(projectionMatrixLocation, false, frameData.leftProjectionMatrix);
      gl.uniformMatrix4fv(viewMatrixLocation, false, frameData.leftViewMatrix);
      drawGeometry();

      // WebVR: Render the right eye???s view to the right half of the canvas
      gl.viewport(canvas.width * 0.5, 0, canvas.width * 0.5, canvas.height);
      gl.uniformMatrix4fv(projectionMatrixLocation, false, frameData.rightProjectionMatrix);
      gl.uniformMatrix4fv(viewMatrixLocation, false, frameData.rightViewMatrix);
      drawGeometry();

      function drawGeometry() {
        // draw the view for each eye
      }

        ...

      // WebVR: Indicate that we are ready to present the rendered frame to the VR display
      vrDisplay.submitFrame();
    }

**Note**: You can see this complete code at [raw-webgl-example](https://github.com/mdn/webvr-tests/blob/master/raw-webgl-example/webgl-demo.js).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#interface-vrpose">WebVR 1.1<br />
<span class="small">The definition of 'VRPose' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`VRPose`

No

???18-79

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

`angularVelocity`

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

`hasOrientation`

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

`hasPosition`

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

`linearAcceleration`

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

`linearVelocity`

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

`orientation`

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

`position`

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

`timestamp`

No

15-79

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

-   [WebVR API homepage](webvr_api)
-   <https://mixedreality.mozilla.org/> ??? demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRPose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRPose</a>
