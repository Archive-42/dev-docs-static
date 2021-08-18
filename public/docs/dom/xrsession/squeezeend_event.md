XRSession: squeezeend event
===========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The WebXR event `squeezeend` is sent to an [`XRSession`](../xrsession) when one of its input sources ends its [primary action](../webxr_device_api/inputs#primary_squeeze_actions) or when an input source that's in the process of handling an ongoing primary action is disconnected without successfully completing the action. Primary squeeze actions include things like users pressing triggers or buttons, tapping a touchpad, speaking a command, or performing a recognizable gesture when using a video tracking system or handheld controller with an accelerometer.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../xrinputsourceevent"><code>XRInputSourceEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onsqueezeend"><code>onsqueezeend</code></a></td></tr></tbody></table>

For details on how the [`squeezestart`](squeezestart_event), [`squeeze`](squeeze_event), and [`squeezeend`](squeezeend_event) events work, and how you should react to them, see [Primary squeeze actions](../webxr_device_api/inputs#primary_squeeze_actions) in [Inputs and input sources](../webxr_device_api/inputs).

Examples
--------

The following example uses [`addEventListener()`](../eventtarget/addeventlistener) to establish handlers for the squeezeion events: [`squeezestart`](squeezestart_event), [`squeezeend`](squeezeend_event), and [`squeeze`](squeeze_event). This snippet is the core of an event handler to allow the user to grab objects in the scene and move them around.

In this case, a single function is used to handle all three events, allowing them to share certain code that's the same regardless of which of the three events is received. Only after completing those tasks does the `onSqueezeEvent()` function below dispatch the action out to a specialized function to handle things.

After checking to ensure that the received event is a `tracked-pointer` event (the only kind we handle here), the target ray's pose is obtained using [`getPose()`](../xrframe/getpose).

If the target ray pose was fetched successfully, the code then uses the value of [`Event`](../event) property [`type`](../event/type) to route control to an appropriate function to handle the event which arrived:

-   For `squeezestart` events, a `myBeginTracking()` function is called with the target ray pose's [`matrix`](../xrrigidtransform/matrix). The `myBeginTracking()` function would presumably start the presentation of the object-dragging process, using the transform to perform a hit test, determining which object to pick up. `myBeginTracking()` returns an object representing the object the user has begun to drag.
-   Upon receiving a `squeeze` event, the `myDropObject()` function is called with the target object and the current target ray pose transform as inputs. This places the object into its new position in the world and triggers any effects that may arise from doing so (like scheduling an animation of a splash if dropped in water, etc).
-   The `squeezeend` event results in a `myStopTracking()` function being called with the object being dragged and the final target ray pose's transform.

<!-- -->

    xrSession.addEventListener("squeezestart", onSqueezeEvent);
    xrSession.addEventListener("squeeze", onSqueezeEvent);
    xrSession.addEventListener("squeezeend", onSqueezeEvent);

    function onSqueezeEvent(event) {
      let source = event.inputSource;
      let targetObj = null;

      if (source.targetRayMode != "tracked-pointer") {
        return;
      }

      let targetRayPose = event.frame.getPose(source.targetRaySpace, myRefSpace);
      if (!targetRayPose) {
        return;
      }

      switch(event.type) {
        case "squeezestart":
          targetObj = myBeginTracking(targetRayPose.matrix);
          break;
        case "squeeze":
          myDropObject(targetObj, targetRayPose.matrix);
          break;
        case "squeezeend":
          myStopTracking(targetObj, targetRayPose.matrix);
          break;
      }
    }

You can of course also set up a handler these events by setting the [`XRSession`](../xrsession) object's [`onsqueezeend`](onsqueezeend) event handler property to a function that handles the event:

    xrSession.onsqueezestart = onSqueezeEvent;
    xrSession.onsqueeze = onSqueezeEvent;
    xrSession.onsqueezeend = onSqueezeEvent;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#eventdef-xrsession-squeezeend">WebXR Device API<br />
<span class="small">The definition of 'squeezeend event' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRSession.squeezeend_event`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/squeezeend_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/squeezeend_event</a>
