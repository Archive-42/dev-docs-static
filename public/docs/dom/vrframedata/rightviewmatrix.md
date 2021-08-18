VRFrameData.rightViewMatrix
===========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `rightViewMatrix` read-only property of the [`VRFrameData`](../vrframedata) interface returns a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) representing a 4x4 matrix that describes the view transform to be used for the right eye’s rendering.

This value may be passed directly to WebGL’s [`uniformMatrix4fv`](../webglrenderingcontext/uniformmatrix) function.

**Important**: It is highly recommended that applications use this matrix when rendering.

Syntax
------

    var myRVM = vrFrameDataInstance.rightViewMatrix;

### Value

A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) object.

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

      // WebVR: Render the left eye’s view to the left half of the canvas
      gl.viewport(0, 0, canvas.width * 0.5, canvas.height);
      gl.uniformMatrix4fv(projectionMatrixLocation, false, frameData.leftProjectionMatrix);
      gl.uniformMatrix4fv(viewMatrixLocation, false, frameData.leftViewMatrix);
      drawGeometry();

      // WebVR: Render the right eye’s view to the right half of the canvas
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vrframedata-rightviewmatrix">WebVR 1.1<br />
<span class="small">The definition of 'rightViewMatrix' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`rightViewMatrix`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRFrameData/rightViewMatrix" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRFrameData/rightViewMatrix</a>
