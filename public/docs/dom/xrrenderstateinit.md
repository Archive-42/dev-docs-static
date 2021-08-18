XRRenderStateInit
=================

**Draft**

This page is not complete.

The `XRRenderStateInit` dictionary is a writeable version of the [`XRRenderState`](xrrenderstate) interface, and is used when calling an [`XRSession`](xrsession)'s [`updateRenderState()`](xrsession/updaterenderstate) method to apply changes to the render state prior to rendering the next frame.

All distances are specified as floating-point values in [meters](https://en.wikipedia.org/wiki/Meter); you can specify a value of 50 centimeters using a value of 0.5, for example.

Properties
----------

 `baseLayer` <span class="badge inline optional">Optional</span>   
An [`XRWebGLLayer`](xrwebgllayer) object from which the WebXR compositor will obtain imagery. This is `null` by default.

 `depthFar` <span class="badge inline optional">Optional</span>   
A floating-point value specifying the distance in meters from the viewer to the **far clip plane**, which is a plane parallel to the display surface beyond which no further rendering will occur. All rendering will take place between the distances specified by `depthNear` and `depthFar`. This is 1000 meters (1 kilometer) by default.

 `depthNear` <span class="badge inline optional">Optional</span>   
A floating-point value indicating the distance in meters from the viewer to a plane parallel to the display surface to be the **near clip plane**. No part of the scene on the viewer's side of this plane will be rendered. This is 0.1 meters (10 centimeters) by default.

 `inlineVerticalFieldOfView` <span class="badge inline optional">Optional</span>   
A floating-point value indicating the default field of view, in radians, to be used when computing the projection matrix for an `inline` [`XRSession`](xrsession). The projection matrix calculation also takes into account the output canvas's aspect ratio. This property *must not* be specified for immersive sessions, so the value is `null` by default for immersive sessions. The default value is otherwise π \* 0.5 (half of the value of pi).

Usage notes
-----------

Any properties not specified in the `XRRenderStateInit` compliant object passed into [`updateRenderState()`](xrsession/updaterenderstate) are left at their current values.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dictdef-xrrenderstateinit">WebXR Device API<br />
<span class="small">The definition of 'XRRenderStateInit' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRRenderStateInit`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [WebXR Device API](webxr_device_api)
-   [`XRRenderState`](xrrenderstate)
-   [`XRSession.renderState`](xrsession/renderstate)
-   [`XRSession.updateRenderState()`](xrsession/updaterenderstate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRRenderStateInit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRRenderStateInit</a>
