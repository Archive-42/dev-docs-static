XRSession.onselect
==================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `onselect` property of the [`XRSession`](../xrsession) object is the event handler for the [`select`](select_event) event, which is dispatched when a [primary action](en-us/docs/web/api/webxr_device_api/inputs#Primary_actions) is completed successfully by the user. This typically represents the pressing of a button or trigger, a hand gesture, or a spoken command.

The [`select`](select_event) event is sent after tracking of the primary action begins, as announced by the [`selectstart`](selectstart_event) event, and immediately before the tracking of the primary action ends, which is announced by the [`selectend`](selectend_event) event.

To learn more about how WebXR actions work, see [Inputs and input sources](../webxr_device_api/inputs).

Syntax
------

    xrSession.onselect = selectHandlerFunction;

### Value

An event handler function to be invoked when the [`XRSession`](../xrsession) receives a [`select`](select_event) event.

Example
-------

This example handles `select` event which occur on the user's main hand (as given by a `user` object's `handedness` property); if that value matches the value of the [`XRInputSource`](../xrinputsource) property [`handedness`](../xrinputsource/handedness), we know that the device is held in the user's main hand.

    xrSession.onselect = event => {
      let source = event.inputSource;

      if (source.handedness == user.handedness) {
        if (source.targetRayMode == "tracked-pointer") {
          let targetRayPose = event.frame.getPose(source.targetRaySpace, myRefSpace);

          if (targetRayPose) {
            myHandleSelectWithRay(targetRayPose);
          }
        }
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-onselect">WebXR Device API<br />
<span class="small">The definition of 'XRSession.onselect' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onselect`

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

-   [Inputs and input sources](../webxr_device_api/inputs)
-   [`XRSession.onselectstart`](onselectstart)
-   [`XRSession.onselectend`](onselectend)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onselect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onselect</a>
