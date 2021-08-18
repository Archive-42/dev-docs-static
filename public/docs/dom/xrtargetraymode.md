XRTargetRayMode
===============

The [WebXR Device API](webxr_device_api) enumerated type `XRTargetRayMode` describes the method by an input controller's targeting ray is being produced. Targeting may be done by looking at the target using a gaze-tracking system, pointing at the target with a hand controller, glove, or motion-tracking system, or by tapping or clicking on the target using a finger on a screen or with a mouse.

Typically a **target ray** is drawn from the source of the targeting system along the target ray in the direction in which the user is looking or pointing. The style of the ray is generally up to you, as is the method for indicating the endpoint of the ray. The targeted point or object might be indicated by drawing a shape or highlighting the targeted surface or object.

<figure><img src="https://developer.mozilla.org/en-US/docs/Web/API/XRTargetRayMode/example-target-ray.gif" alt="A target ray emitted by a hand controller." width="480" height="281" /><figcaption><strong>A target ray emitted by a hand controller.</strong></figcaption></figure>The target ray can be anything from a simple line (ideally fading over distance) to an animated effect, such as the science-fiction "phaser" style shown in the screenshot above.

Values
------

`gaze`  
The user is using a gaze-tracking system (or **gaze input**) which detects the direction in which the user is looking. The target ray will be drawn originating at the viewer's eyes and will follow the direction in which they're looking.

`screen`  
The direction of the target ray is indicated using a tap on a touch screen, mouse, or other tactile input device.

`tracked-pointer`  
Targeting is being performed using a handheld device or hand-tracking system which the user points in the direction of the target. The target ray extends from the hand (or the object in the hand) in the targeted direction. The direction is determined using platform-specific rules, though if no such rules exist, the direction is chosen by assuming the user is pointing their index finger straight out from their hand.

Examples
--------

This fragment of code shows part of a function to be called once every frame. It looks for inputs which have a non-`null` [`targetRaySpace`](xrinputsource/targetrayspace). Inputs which have a value for this property represent inputs that project a target ray outward from the user.

For each such input, this example looks for inputs whose [`targetRayMode`](xrinputsource/targetraymode) is `tracked-pointer`, indicating that the input is in fact intended to represent a targeting device rather than a gazing device, screen tap, or mouse click. For tracked pointers, a function `myRenderTargetRayAsBeam()` is called to render a beam from the input controller's virtual position outward in the direction it's pointing.

The code should continue to perform tasks such as drawing controllers or any objects representative of the user's hands' positions in the virtual space, as well as any other input-related tasks.

    function updateInputSources(session, frame, refSpace) {
      for (let source of session.getInputSources()) {
        let targetRayPose = frame.getPose(inputSource.targetRaySpace, refSpace);

        if (targetRayPose) {
          if (source.targetRayMode == "tracked-pointer") {
            myRenderTargetRayAsBeam(targetRayPose);
          }
        }

        /* ... */
      }
    }

See the article [Inputs and input sources](webxr_device_api/inputs) for more details and a more complete example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#enumdef-xrtargetraymode">WebXR Device API<br />
<span class="small">The definition of 'XRTargetRayMode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRTargetRayMode`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [WebXR Device API](webxr_device_api)
-   [Inputs and input sources](webxr_device_api/inputs)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRTargetRayMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRTargetRayMode</a>
