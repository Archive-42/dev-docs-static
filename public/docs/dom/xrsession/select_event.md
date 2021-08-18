XRSession: select event
=======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The WebXR event `select` is sent to an [`XRSession`](../xrsession) when one of the session's input sources has completed a [primary action](../webxr_device_api/inputs#primary_actions). Examples of comon kinds of primary action are users pressing triggers or buttons, tapping a touchpad, speaking a command, or performing a recognizable gesture when using a video tracking system or handheld controller with an accelerometer.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../xrinputsourceevent"><code>XRInputSourceEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onselect"><code>onselect</code></a></td></tr></tbody></table>

For details on how the [`selectstart`](selectstart_event), [`select`](select_event), and [`selectend`](selectend_event) events work, and how you should react to them, see [Primary actions](../webxr_device_api/inputs#primary_actions) in [Inputs and input sources](../webxr_device_api/inputs).

Examples
--------

The following example uses [`addEventListener()`](../eventtarget/addeventlistener) to set up a handler for the `select` event. The handler fetches the pose representing the target ray for `tracked-pointer` inputs and sends the pose's transform to a function called `myHandleSelectWithRay()`.

    xrSession.addEventListener("select", event => {
      if (event.inputSource.targetRayMode == "tracked-pointer") {
        let targetRayPose = event.frame.getPose(event.inputSource.targetRaySpace,
                                  myRefSpace);
        if (targetRayPose) {
          myHandleSelectWithRay(targetRayPose.transform);
        }
      }
    });

You can of course also set up a handler for `select` events by setting the [`XRSession`](../xrsession) object's [`onselect`](onselect) event handler property to a function that handles the event:

    xrSession.onselect = event => {
      if (event.inputSource.targetRayMode == "tracked-pointer") {
        let targetRayPose = event.frame.getPose(event.inputSource.targetRaySpace,
                                  myRefSpace);
        if (targetRayPose) {
          myHandleSelectWithRay(targetRayPose.transform);
        }
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#eventdef-xrsession-select">WebXR Device API<br />
<span class="small">The definition of 'select event' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`select_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/select_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/select_event</a>
