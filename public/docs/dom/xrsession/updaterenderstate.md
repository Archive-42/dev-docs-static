XRSession.updateRenderState()
=============================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `updateRenderState()` method of the [`XRSession`](../xrsession) interface of [WebXR API](../webxr_device_api) schedules changes to be applied to the active render state prior to rendering of the next frame.

Syntax
------

    xrSession.updateRenderState(newState)

### Parameters

`newState`  
An object conforming to the [`XRRenderStateInit`](../xrrenderstateinit) dictionary specifying the properties of the session's [`renderState`](renderstate) to update before rendering the next frame.

The specified object may have any combination of the following fields.

 `baseLayer` <span class="badge inline optional">Optional</span>   
An [`XRWebGLLayer`](../xrwebgllayer) object from which the WebXR compositor will obtain imagery. This is `null` by default.

 `depthFar` <span class="badge inline optional">Optional</span>   
A floating-point value specifying the distance in meters from the viewer to the **far clip plane**, which is a plane parallel to the display surface beyond which no further rendering will occur. All rendering will take place between the distances specified by `depthNear` and `depthFar`. This is 1000 meters (1 kilometer) by default.

 `depthNear` <span class="badge inline optional">Optional</span>   
A floating-point value indicating the distance in meters from the viewer to a plane parallel to the display surface to be the **near clip plane**. No part of the scene on the viewer's side of this plane will be rendered. This is 0.1 meters (10 centimeters) by default.

 `inlineVerticalFieldOfView` <span class="badge inline optional">Optional</span>   
A floating-point value indicating the default field of view, in radians, to be used when computing the projection matrix for an `inline` [`XRSession`](../xrsession). The projection matrix calculation also takes into account the output canvas's aspect ratio. This property *must not* be specified for immersive sessions, so the value is `null` by default for immersive sessions. The default value is otherwise π \* 0.5 (half of the value of pi).

### Return value

None.

### Exceptions

This method may throw any of the following exceptions. These are true exceptions, since this method does not return a promise.

`InvalidStateError`  
This may occur for one of the following reasons:

-   The [`XRSession`](../xrsession) has already ended, so you cannot change its render state.
-   The <span class="page-not-created">`baseLayer`</span> specified in `newState` was created by an `XRSession` other than the one on which `updateRenderState()` was called.
-   The <span class="page-not-created">`inlineVerticalFieldOfView`</span> property was set, but the session is immersive and therefore does not allow this property to be used.

Examples
--------

This example creates a WebGL context that is compatible with an immersive XR device and then uses it to create an [`XRWebGLLayer`](../xrwebgllayer). `updateRenderState()` is then called to associate the new `XRWebGLLayer`.

    function onXRSessionStarted(xrSession) {
      let glCanvas = document.createElement("canvas");
      let gl = glCanvas.getContext("webgl", { xrCompatible: true });

      loadWebGLResources();

      xrSession.updateRenderState({ baseLayer: new XRWebGLLayer(xrSession, gl) });
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-updaterenderstate">WebXR Device API<br />
<span class="small">The definition of 'XRSession.updateRenderState()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`updateRenderState`

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
-   [`XRRenderState`](../xrrenderstate)
-   [`XRSession.renderState`](renderstate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/updateRenderState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/updateRenderState</a>
