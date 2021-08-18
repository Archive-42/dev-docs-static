XRInputSource.targetRayMode
===========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRInputSource`](../xrinputsource) property `targetRayMode` indicates the method by which the target ray for the input source should be generated and how it should be presented to the user.

Syntax
------

    let rayMode = xrInputSource.targetRayMode;

### Value

A [`DOMString`](../domstring) taken from the [`XRTargetRayMode`](../xrtargetraymode) enumerated type, indicating which method to use when generating and presenting the target ray to the user. The possible values are:

`gaze`  
The user is using a gaze-tracking system (or **gaze input**) which detects the direction in which the user is looking. The target ray will be drawn originating at the viewer's eyes and will follow the direction in which they're looking.

`screen`  
The direction of the target ray is indicated using a tap on a touch screen, mouse, or other tactile input device.

`tracked-pointer`  
Targeting is being performed using a handheld device or hand-tracking system which the user points in the direction of the target. The target ray extends from the hand (or the object in the hand) in the targeted direction. The direction is determined using platform-specific rules, though if no such rules exist, the direction is chosen by assuming the user is pointing their index finger straight out from their hand.

Usage notes
-----------

The input source's [`targetRaySpace`](targetrayspace) indicates the position and orientation of the target ray, and can be used to determine where to render the ray.

Example
-------

This fragment of code shows part of a function to be called once every frame. It looks for inputs which have a non-`null` [`targetRaySpace`](targetrayspace). Inputs which have a value for this property represent inputs that project a target ray outward from the user.

For each such input, this example looks for inputs whose [`targetRayMode`](targetraymode) is `tracked-pointer`, indicating that the input is in fact intended to represent a targeting device rather than a gazing device, screen tap, or mouse click. For tracked pointers, a function `myRenderTargetRayAsBeam()` is called to render a beam from the input controller's virtual position outward in the direction it's pointing.

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

See the article [Inputs and input sources](../webxr_device_api/inputs) for more details and a more complete example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrinputsource-targetraymode">WebXR Device API<br />
<span class="small">The definition of 'XRInputSource.handedness' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`targetRayMode`

79

79

No

No

No

No

No

79

No

No

No

11.2

See also
--------

-   [WebXR Device API](../webxr_device_api)
-   [Inputs and input sources](../webxr_device_api/inputs)
-   [Using gamepads in WebXR applications](https://developer.mozilla.org/en-US/docs/Web/WebXR%20Device%20API/Gamepads)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSource/targetRayMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSource/targetRayMode</a>
