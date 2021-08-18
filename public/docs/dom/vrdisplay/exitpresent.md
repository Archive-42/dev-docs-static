VRDisplay.exitPresent()
=======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `exitPresent()` method of the [`VRDisplay`](../vrdisplay) interface stops the `VRDisplay` presenting a scene.

Syntax
------

    vrDisplayInstance.exitPresent().then(function() {
      // Do something after the presentation has ended
    });

### Parameters

None.

### Return value

A promise that resolves once the presentation has ended. If the `VRDisplay` is not presenting when `exitPresent()` is called, the promise will reject.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vrdisplay-exitpresent">WebVR 1.1<br />
<span class="small">The definition of 'exitPresent()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [WebVR API homepage](../webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/exitPresent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/exitPresent</a>
