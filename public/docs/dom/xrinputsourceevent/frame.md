XRInputSourceEvent.frame
========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRInputSourceEvent`](../xrinputsourceevent) property `frame` specifies an [`XRFrame`](../xrframe) object representing the event frame during which a [WebXR](../webxr_device_api) user input occurred. This may thus be an event which occurred in the past rather than a current or impending event.

Syntax
------

    let inputFrame = xrInputSourceEvent.frame;

### Value

An [`XRFrame`](../xrframe) indicating the event frame at which the user input event described by the object took place.

Usage notes
-----------

The event frame does not correspond to a visual frame as is delivered to the frame rendering callback function (see [Rendering and the WebXR frame rendering callback](../webxr_device_api/rendering) for details on the callback). Instead, the `XRFrame` specified by the `frame` property is a method to provide access to the [`getPose()`](../xrframe/getpose) method, which you can use to get the relative positions of the objects in the scene at the time the event occurred.

However, since the event frame isn't an animation frame, there is no viewer pose available to represent the viewer's current point of view; the results of calling [`getViewerPose()`](../xrframe/getviewerpose) will be an [`XRViewerPose`](../xrviewerpose) with an empty [`views`](../xrviewerpose/views) list.

Examples
--------

This code shows a handler for the [`selectstart`](../xrsession/selectstart_event) event which gets the target ray's pose from the frame, mapping the pose representing the ray (`event.inputSource.targetRaySpace`) to the overall reference space `myRefSpace`.

Then, if the result isn't `null`, the target ray pose's transform is passed into a function called `myCheckAndHandleHit()` to see if the ray was pointing at anything when the select was triggered.

    xrSession.onselectstart = event => {
      let targetRayPose = event.frame.getPose(event.inputSource.targetRaySpace,
                                myRefSpace);
      if (targetRayPose) {
        checkAndHandleHit(targetRayPose.transform);
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrinputsourceevent-frame">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourceEvent.frame' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`frame`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceEvent/frame" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceEvent/frame</a>
