XRInputSource.targetRaySpace
============================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRInputSource`](../xrinputsource) property `targetRaySpace` returns an [`XRSpace`](../xrspace) (typically an [`XRReferenceSpace`](../xrreferencespace)) representing the position and orientation of the target ray in the virtual space. Its native origin tracks the position of the origin point of the target ray, and its orientation indicates the orientation of the controller device itself. These values, interpreted in the context of the input source's [`targetRayMode`](targetraymode), can be used both to fully interpret the device as an input source.

**&lt;&lt;&lt;--- needs diagram showing targetRaySpace relative to gripSpace and world space ---&gt;&gt;&gt;**

To obtain an `XRSpace` representing the input controller's position and orientation in virtual space, use the [`gripSpace`](gripspace) property.

Syntax
------

    let targetRaySpace = xrInputSource.targetRaySpace;

### Value

An [`XRSpace`](../xrspace) object—typically an [`XRReferenceSpace`](../xrreferencespace) or [`XRBoundedReferenceSpace`](../xrboundedreferencespace)—which represents the position and orientation of the input controller's target ray in virtual space.

The native origin of the returned `XRSpace` is located at the point from which the target ray is emitted, and the orientation of the space indicates the direction in which the target ray is pointing.

Usage notes
-----------

All input sources—regardless of their [`targetRayMode`](targetraymode)—have a valid `targetRaySpace`. The exact meaning of this space varies, however, depending on the mode:

-   Every gaze input (`targetRayMode` value of `gaze`), shares the same [`XRSpace`](../xrspace) object as their target ray space, since the gaze input comes from the viewer's head. This shared space represents the same location as the space returned by the [`XRSession`](../xrsession) method [`requestReferenceSpace()`](../xrsession/requestreferencespace), but is maintained as a different object to allow for future enhancements to the API.
-   The target ray space reported by tracked pointer inputs (`targetRayMode` of `tracked-pointer`) is actually based upon the true spatial position and orientation of the input device.

To determine the position and orientation of the target ray while rendering a frame, pass it into the [`XRFrame`](../xrframe) method [`getPose()`](../xrframe/getpose) method, then use the returned [`XRPose`](../xrpose) object's [`transform`](../xrpose/transform) to gather the spatial information you need.

Example
-------

This fragment of code shows part of a function to be called once every frame. It looks for inputs which have a non-`null` [`targetRaySpace`](targetrayspace). Inputs which have a value for this property represent inputs that project a target ray outward from the user.

For each such input, this example looks for inputs whose [`targetRayMode`](targetraymode) is `tracked-pointer`, indicating that the input is in fact intended to represent a targeting device rather than a gazing device, screen tap, or mouse click. For tracked pointers, a function `myRenderTargetRayAsBeam()` is called to render a beam from the input controller's virtual position outward in the direction it's pointing.

The code should continue to perform tasks such as drawing controllers or any objects representative of the user's hands' positions in the virtual space, as well as any other input-related tasks.

    function updateInputSources(session, frame, refSpace) {
      for (let source of session.getInputSources()) {
        let targetRayPose = frame.getPose(inputSource.targetRaySpace, refSpace);

        if (targetRayPose) {
          if (source.targetRayMode == "tracked-pointer") {
            myRenderTargetRayAsBeam(targetRayPose);
          }
        }

        /* ... */
      }
    }

See the article [Inputs and input sources](../webxr_device_api/inputs) for more details and a more complete example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrinputsource-targetrayspace">WebXR Device API<br />
<span class="small">The definition of 'XRInputSource.targetRaySpace' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`targetRaySpace`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSource/targetRaySpace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSource/targetRaySpace</a>
