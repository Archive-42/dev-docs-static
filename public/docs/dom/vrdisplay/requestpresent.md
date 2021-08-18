VRDisplay.requestPresent()
==========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `requestPresent()` method of the [`VRDisplay`](../vrdisplay) interface starts the `VRDisplay` presenting a scene.

Syntax
------

    vrDisplayInstance.requestPresent(layers).then(function() {
      // Do something after the presentation has begun
    });

### Parameters

layers  
An array of [`VRLayerInit`](../vrlayerinit) objects representing the scene you want to present. At the moment, this can be a minimum of 0 and a maximum of 1.

### Return value

A promise that resolves once the presentation has begun. there are a number of rules surrounding the promise's fulfillment or rejection:

-   If [`VRDisplayCapabilities.canPresent`](../vrdisplaycapabilities/canpresent) is false, or if the VRLayer array contains more than [`VRDisplayCapabilities.maxLayers`](../vrdisplaycapabilities/maxlayers) layers, the promise will be rejected.
-   If the [`VRDisplay`](../vrdisplay) is already presenting when `requestPresent()` is called, the `VRDisplay` will update the `VRLayer` array being presented.
-   If a call to `requestPresent()` is rejected while the `VRDisplay` is already presenting it will end its presentation.
-   If `requestPresent()` is called outside of an engagement gesture the promise will be rejected unless the `VRDisplay` was already presenting. This engagement gesture is also sufficient to allow `requestPointerLock()` calls until presentation has ended.

Examples
--------

    if(navigator.getVRDisplays) {
      console.log('WebVR 1.1 supported');
      // Then get the displays attached to the computer
      navigator.getVRDisplays().then(function(displays) {
        // If a display is available, use it to present the scene
        if(displays.length > 0) {
          vrDisplay = displays[0];
          console.log('Display found');
          // Starting the presentation when the button is clicked: It can only be called in response to a user gesture
          btn.addEventListener('click', function() {
            if(btn.textContent === 'Start VR display') {
              vrDisplay.requestPresent([{ source: canvas }]).then(function() {
                console.log('Presenting to WebVR display');

                // Set the canvas size to the size of the vrDisplay viewport

                var leftEye = vrDisplay.getEyeParameters('left');
                var rightEye = vrDisplay.getEyeParameters('right');

                canvas.width = Math.max(leftEye.renderWidth, rightEye.renderWidth) * 2;
                canvas.height = Math.max(leftEye.renderHeight, rightEye.renderHeight);

                // stop the normal presentation, and start the vr presentation
                window.cancelAnimationFrame(normalSceneFrame);
                drawVRScene();

                btn.textContent = 'Exit VR display';
              });
            } else {
              vrDisplay.exitPresent();
              console.log('Stopped presenting to WebVR display');

              btn.textContent = 'Start VR display';

              // Stop the VR presentation, and start the normal presentation
              vrDisplay.cancelAnimationFrame(vrSceneFrame);
              drawScene();
            }
          });
        }
      });
    }

**Note**: You can see this complete code at [raw-webgl-example](https://github.com/mdn/webvr-tests/blob/master/raw-webgl-example/webgl-demo.js).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vrdisplay-requestpresent">WebVR 1.1<br />
<span class="small">The definition of 'requestPresent()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [WebVR API homepage](../webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/requestPresent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/requestPresent</a>
