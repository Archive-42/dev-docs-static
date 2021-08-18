XRSession: squeeze event
========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The WebXR event `squeeze` is sent to an [`XRSession`](../xrsession) when one of the session's input sources has completed a [primary squeeze action](../webxr_device_api/inputs#primary_squeeze_actions). Examples of comon kinds of primary action are users pressing triggers or buttons, tapping a touchpad, speaking a command, or performing a recognizable gesture when using a video tracking system or handheld controller with an accelerometer.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../xrinputsourceevent"><code>XRInputSourceEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onsqueeze"><code>onsqueeze</code></a></td></tr></tbody></table>

For details on how the [`squeezestart`](squeezestart_event), [`squeeze`](squeeze_event), and [`squeezeend`](squeezeend_event) events work, and how you should react to them, see [Primary squeeze actions](../webxr_device_api/inputs#primary_squeeze_actions) in [Inputs and input sources](../webxr_device_api/inputs).

Examples
--------

The following example uses [`addEventListener()`](../eventtarget/addeventlistener) to set up a handler for the `squeeze` event. The handler fetches the pose representing the target ray for `tracked-pointer` inputs and sends the pose's transform to a function called `myHandleSqueezeWithRay()`.

This code treats the squeeze as an instantaneous action that doesn't involve tracking an ongoing activity. If you need to track a squeeze action that isn't instantaneous, listen for the [`squeezestart`](squeezestart_event) and [`squeezeend`](squeezeend_event) events to sense when the squeeze action begins and ends.

    xrSession.addEventListener("squeeze", event => {
      if (event.inputSource.targetRayMode == "tracked-pointer") {
        let targetRayPose = event.frame.getPose(event.inputSource.targetRaySpace,
                                  myRefSpace);
        if (targetRayPose) {
          myHandleSqueezeWithRay(targetRayPose.transform);
        }
      }
    });

You can of course also set up a handler for `squeeze` events by setting the [`XRSession`](../xrsession) object's [`onsqueeze`](onsqueeze) event handler property to a function that handles the event:

    xrSession.onsqueeze = event => {
      if (event.inputSource.targetRayMode == "tracked-pointer") {
        let targetRayPose = event.frame.getPose(event.inputSource.targetRaySpace,
                                  myRefSpace);
        if (targetRayPose) {
          myHandleSqueezeWithRay(targetRayPose.transform);
        }
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#eventdef-xrsession-squeeze">WebXR Device API<br />
<span class="small">The definition of 'squeeze event' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRSession.squeeze_event`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/squeeze_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/squeeze_event</a>
