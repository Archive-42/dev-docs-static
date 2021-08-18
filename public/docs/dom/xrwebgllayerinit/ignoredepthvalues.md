XRWebGLLayerInit.ignoreDepthValues
==================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRWebGLLayerInit`](../xrwebgllayerinit) dictionary's Boolean `ignoreDepthValues` property can be provided in the options passed into the [`XRWebGLLayer()`](../xrwebgllayer/xrwebgllayer) constructor to indicate that the depth buffer, if it exists, should be ignored while composing the scene.

The depth buffer is typically used to assist in ordering vertices and, by extension, polygons while compositing, to ensure that the scene is correctly composited, with objects the correct distance away and with clipping and other distance-related computations performed as accurately as possible. Without the depth buffer, these computations must rely entirely on the coordinates of each pixel.

This property differs from [`depth`](depth) in that `depth` requests a WebGL layer that does not have a depth buffer at all, while `ignoreDepthValues` merely asks that the depth layer be ignored.

Syntax
------

    let layerInit = {
      ignoreDepthValues: boolValue
    };
    let glLayer = new XRWebGLLayer(xrSession, gl, layerInit);

    let glLayer = new XRWebGLLayer(xrSession, gl, { ignoreDepthValues: boolValue });

### Value

A Boolean value which can be set to `true` to disable the use of the depth buffer by the WebGL rendering layer created by the [`XRWebGLLayer()`](../xrwebgllayer/xrwebgllayer) constructor. The default value, `false`, means the depth buffer *will* be used, if available.

Usage notes
-----------

If `ignoreDepthValues` is `true`, the WebXR compositor will ignore the contents of the depth buffer, if it exists, while compositing and rendering the scene. If `false`, the depth buffer's contents are used, if one is present.

Using a depth buffer while compositing allows the XR compositor to help ensure the compositing is done as accurately as possible. Each entry in the depth buffer corresponds to the depth of the fragment whose color is at the same location in the color buffer, and must have a value between 0.0 and 1.0, where 0.0 corresponds to the distance specified in the [`XRSession`](../xrsession) object's [`renderState`](../xrsession/renderstate) record's [`depthNear`](../xrrenderstate/depthnear) and 1.0 represents the distance given by [`depthFar`](../xrrenderstate/depthfar).

Ignoring depth values causes the compositor to rely solely upon the relative position of objects to establish depth, and may result in less effective and less comfortable 3D effects. The default is `false` (depth values are used by default).

Example
-------

In this example, a new [`XRWebGLLayer`](../xrwebgllayer) is created for a WebXR session, `xrSession`. It's configured to ignore depth values or an alpha channel.

    xrSession.updateRenderState({
      baseLayer: new XRWebGLLayer(xrSession, gl, {
         alpha: false,
         ignoredepthValues: true
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrwebgllayerinit-ignoredepthvalues">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayerInit.ignoreDepthValues' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ignoreDepthValues`

79

79

No

No

No

No

79

79

No

No

No

11.2

See also
--------

-   [WebXR Device API](../webxr_device_api)
-   [Getting started with WebGL](../webgl_api/tutorial/getting_started_with_webgl)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit/ignoreDepthValues" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit/ignoreDepthValues</a>
