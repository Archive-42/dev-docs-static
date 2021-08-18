XRSession.onsqueezestart
========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRSession`](../xrsession) interface's `onsqueezestart` event handler property can be set to a function which is then invoked to handle the [`squeezestart`](squeezestart_event) event that's sent when the user successfully begins a [primary squeeze action](../webxr_device_api/inputs#primary_squeeze_actions) on a WebXR input device. These actions represent the user squeezing or tightly gripping an object or controller.

To learn more about how to use and handle WebXR controller inputs, see [Inputs and input sources](../webxr_device_api/inputs).

Syntax
------

    xrSession.onsqueezestart = squeezestartHandlerFunction;

### Value

A function to be invoked whenever the [`XRSession`](../xrsession) receives a [`squeezestart`](squeezestart_event) event.

Examples
--------

This snippet of code adds a simple handler for the `squeezestart` event, which responds only to events on the user's dominant hand by getting the target ray, then calling a function `findObjectUsingRay()` to identify the object that the user is pointing at. This object is then stored in a `heldObject` variable in the `user` object we're using to represent user information.

    xrSession.onsqueezestart = event => {
      if (event.inputSource.handedness == user.handedness) {
        let targetRayPose = event.frame.getPose(event.inputSource.targetRaySpace, myRefSpace;

        if (targetRayPose) {
          user.heldObject = findObjectUsingRay(targetRayPose.transform);
        }
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-onsqueezestart">WebXR Device API<br />
<span class="small">The definition of 'XRSession.onsqueezestart' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onsqueezestart`

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
-   The other `onsqueeze*` handlers: [`onsqueeze`](onsqueeze) and [`onsqueezeend`](onsqueezeend)
-   The [`squeeze`](squeeze_event), [`squeezestart`](squeezestart_event), and [`squeezeend`](squeezeend_event) events

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onsqueezestart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onsqueezestart</a>
