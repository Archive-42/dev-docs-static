XRPose.transform
================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `transform` read-only attribute of the [`XRPose`](../xrpose) interface is a [`XRRigidTransform`](../xrrigidtransform) object providing the position and orientation of the pose relative to the base [`XRSpace`](../xrspace) as specified when the pose was obtained by calling [`XRFrame.getPose()`](../xrframe/getpose).

Syntax
------

    let poseTransform = xrPose.transform;

### Value

An [`XRRigidTransform`](../xrrigidtransform) which provides the position and orientation of the [`XRPose`](../xrpose) relative to the [`XRFrame`](../xrframe) to which this `XRPose` is aligned. This is the same pose that's returned by the frame's [`getPose()`](../xrframe/getpose) method.

Example
-------

This handler for the [`XRSession`](../xrsession) event [`select`](../xrsession/select_event) handles events for tracked pointers. It determines the targeted object by passing the event frame's pose into a function called `findTargetUsingRay()`, then dispatches the event differently depending on the user's handedness; this is done by comparing the value of the [`XRInputSource`](../xrinputsource) property [`handedness`](../xrinputsource/handedness) to a value in the variable `user.handedness`. If the source is a controller in the user's primary hand, a function is called on the targeted object called `primaryAction()`; otherwise, it calls the targeted object's `offHandAction()` function.

    xrSession.addEventListener("select", event => {
      let source = event.inputSource;
      let frame = event.frame;
      let targetRayPose = frame.getPose(source.targetRaySpace, myRefSpace);
      let targetObject = findTargetUsingRay(targetRay.transform.matrix);

      if (source.targetRayMode == "tracked-pointer") {
        if (source.handedness == user.handedness) {
          targetObject.primaryAction();
        } else {
          targetObject.offHandAction();
        }
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrpose-transform">WebXR Device API<br />
<span class="small">The definition of 'XRPose.transform' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`transform`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRPose/transform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRPose/transform</a>
