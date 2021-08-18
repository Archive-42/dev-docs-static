XRInputSource.handedness
========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRInputSource`](../xrinputsource) property `handedness` indicates which of the user's hands the WebXR input source is associated with, or if it's not associated with a hand at all.

Syntax
------

    let hand = xrInputSource.handedness;

### Value

A [`DOMString`](../domstring) indicating whether the input controller is held in one of the user's hands, and if it is, which hand. The value, which comes from the [`XRHandedness`](../xrhandedness) enumerated type, is one of the following:

`none`  
The input controller is not associated with one of the user's hands.

`left`  
The input controller is being held in, worn on, or is attached to the user's left hand.

`right`  
The input controller is being held in, worn on, or is attached to the user's right hand.

Usage notes
-----------

If the input source is not a device associated with a user's hand (whether by being held, attached, or worn), the value of `handedness` is `none`. This may indicate, for example, an input source which isn't hand-held, such as controls built into a headset or an input device attached to the head or body.

Examples
--------

One important usage scentario for `handedness` is to determine which hand a controller is in so you can draw a representation of that hand (or the device that hand is controlling) in virtual space.

    function updateInputSources(session, frame, refSpace) {
      for (let source of session.inputSources) {
        if (source.gripSpace) {
          let gripPose = frame.getPose(source.gripSpace, refSpace);

          if (gripPose) {
            myRenderHandObject(gripPose, inputSource.handedness);
          }
        }
      }
    }

This function, which would be called every animation frame (or possibly just periodically, depending on the degree of smoothness required and any performance constraints), scans the list of input sources looking for any which have a [`gripSpace`](gripspace) which isn't `null`. If a `gripSpace` is present, that means the input source is a hand-held device of some sort, so it should be rendered visibly if possible.

If `gripSpace` is non-`null`, the function proceeds to get the pose for the `gripSpace` transformed into the current reference space. Assuming that's then valid, a function called `myRenderHandObject()` is called with the grip's pose and the value of `handedness`. With these values in hand (no pun intended), `myRenderHandObject()` can draw the appropriate model positioned and formed for the correct hand.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrinputsource-handedness">WebXR Device API<br />
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

`handedness`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSource/handedness" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSource/handedness</a>
