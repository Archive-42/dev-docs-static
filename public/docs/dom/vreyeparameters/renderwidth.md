VREyeParameters.renderWidth
===========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `renderWidth` read-only property of the [`VREyeParameters`](../vreyeparameters) interface describes the recommended render target width of each eye viewport, in pixels.

This is already in device pixel units, so there's no need to multiply by [Window.devicePixelRatio](../window/devicepixelratio) before setting to [HTMLCanvasElement.width.](../htmlcanvaselement/width)

Syntax
------

    var myRenderWidth = eyeParametersInstance.renderWidth;

### Value

A number, representing the width in pixels.

Examples
--------

    navigator.getVRDisplays().then(function(displays) {
      // If a display is available, use it to present the scene
      vrDisplay = displays[0];
      console.log('Display found');
      // Starting the presentation when the button is clicked:
      //   It can only be called in response to a user gesture
      btn.addEventListener('click', function() {
        vrDisplay.requestPresent([{ source: canvas }]).then(function() {
          console.log('Presenting to WebVR display');

          // Set the canvas size to the size of the vrDisplay viewport

          var leftEye = vrDisplay.getEyeParameters('left');
          var rightEye = vrDisplay.getEyeParameters('right');

          canvas.width = Math.max(leftEye.renderWidth, rightEye.renderWidth) * 2;
          canvas.height = Math.max(leftEye.renderHeight, rightEye.renderHeight);

          drawVRScene();
        });
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vreyeparameters-renderwidth">WebVR 1.1<br />
<span class="small">The definition of 'renderWidth' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`renderWidth`

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

-   [WebVR API homepage](../webvr_api).
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VREyeParameters/renderWidth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VREyeParameters/renderWidth</a>
