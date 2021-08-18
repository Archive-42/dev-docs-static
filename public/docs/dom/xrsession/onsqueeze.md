XRSession.onsqueeze
===================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRSession`](../xrsession) interface's `onsqueeze` event handler property can be set to a function which is then invoked to handle the [`squeeze`](squeeze_event) event that's sent when the user successfully completes a [primary squeeze action](../webxr_device_api/inputs#primary_squeeze_actions) on a WebXR input device. These actions represent the user squeezing or gripping an object or controller.

To learn more about how to use and handle WebXR controller inputs, see [Inputs and input sources](../webxr_device_api/inputs).

Syntax
------

    xrSession.onsqueeze = squeezeHandlerFunction;

### Value

A function to be invoked whenever the [`XRSession`](../xrsession) receives a [`squeeze`](squeeze_event) event.

Examples
--------

### Handling squeeze events for a specific hand

This snippet of code adds a simple handler for the `squeeze` event, which responds only to events on the user's off-hand (that is, the hand that isn't their dominant hand). This is determined by comparing the input source's [`handedness`](../xrinputsource/handedness) against the value of a `handedness` property on a `user` object we've established previously.

    xrSession.onsqueeze = event => {
      if (event.inputSource.handedness != user.handedness) {
        handleOffhandSqueeze(event.inputSource, event.frame);
      }
    };

### Finishing an ongoing squeeze action

This example exapnds somewhat on the previous example by demonstrating a way to implement the ability for the user to drop an object that was previously picked up by the user.. This is just a snippet of code, but should establish the general idea.

After checking that the event occurred on the user's dominant hand, the pose's target ray is obtained. Then we pass the currently held object and the target ray's transform matrix into a function we call `dropObjectUsingRay()` to drop the object, using the target ray to determine the surface upon which the object should be placed. This also clears the value of `heldObject` so we know that there's no longer an object in hand.

    xrSession.onsqueeze = event => {
      if (event.inputSource.handedness == user.handedness) {
        let targetRayPose = event.frame.getPose(event.inputSource.targetRaySpace, myRefSpace);

        if (user.heldObject && targetRayPose) {
          dropObjectUsingRay(user.heldObject, targetRayPose.transform.matrix):
        }
      }
    };

See the examples in the [`onsqueezestart`](onsqueezestart) and [`onsqueezeend`](onsqueezeend) event handlers for the reset of the event handling related to this approach.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-onsqueeze">WebXR Device API<br />
<span class="small">The definition of 'XRSession.onsqueeze' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onsqueeze`

83

83

No

No

No

No

No

83

No

No

No

13.0

See also
--------

-   [Inputs and input sources](../webxr_device_api/inputs)
-   The other `onsqueeze*` handlers: [`onsqueezestart`](onsqueezestart) and [`onsqueezeend`](onsqueezeend)
-   The [`squeeze`](squeeze_event), [`squeezestart`](squeezestart_event), and [`squeezeend`](squeezeend_event) events

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onsqueeze" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onsqueeze</a>
