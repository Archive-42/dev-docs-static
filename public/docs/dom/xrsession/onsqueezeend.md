XRSession.onsqueezeend
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRSession`](../xrsession) interface's `onsqueezeend` event handler property is a function to be invokedn when the [`squeezeend`](squeezeend_event) event sent to an `XRSession` when a [primary squeeze action](../webxr_device_api/inputs#primary_squeeze_actions) ends. This is sent immediately after the [`squeeze`](squeeze_event) event, which announces the *successful* completion of the squeeze action. The `squeezeend` event handler is where you handle closing out a squeeze action whether it was successfully completed or not.

To learn more about how the sequence of squeeze events works, see [Primary squeeze actions](#) in [Inputs and input sources](../webxr_device_api/inputs).

Syntax
------

    xrSession.onsqueezeend = squeezeendHandlerFunction;

### Value

A function to be invoked whenever the [`XRSession`](../xrsession) receives a [`squeezestart`](squeezeend_event) event, indicating the ending of a primary squeeze action.

Examples
--------

This snippet of code adds a simple handler for the `squeezeend` event, which responds only to events on the user's dominant hand. In response to the end of the squeeze operation, this code looks to see if there is an object currently being held by the user by checking to see if the variable `user.heldObject` contains a reference to an object representing the held item.

If `heldObject` has an object reference, that object is passed to a function called `cancelObjectDrag()`, which would be written to return the object to its original position. This takes care of the situation in which the drag is aborted or canceled.

    xrSession.onsqueezeend = event => {
      if (event.inputSource.handedness == user.handedness) {
        let targetRayPose = event.frame.getPose(event.inputSource.targetRaySpace, myRefSpace;

        if (user.heldObject) {
           cancelObjectDrag(user.heldObject);
        }
      }
    };

This code presumes that if the user actually intentionally completed the drag, `user.heldObject` will be `null` here. That's because (in this example, at least) the handler for the [`squeeze`](squeeze_event) event has already dropped the object into its new location and then cleared the value of `heldObject` to indicate that the user is no longer holding anything.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-onsqueezeend">WebXR Device API<br />
<span class="small">The definition of 'XRSession.onsqueezeend' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onsqueezeend`

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
-   The other `onsqueeze*` handlers: [`onsqueezestart`](onsqueezestart) and [`onsqueeze`](onsqueeze)
-   The [`squeeze`](squeeze_event), [`squeezestart`](squeezestart_event), and [`squeezeend`](squeezeend_event) events

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onsqueezeend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onsqueezeend</a>
