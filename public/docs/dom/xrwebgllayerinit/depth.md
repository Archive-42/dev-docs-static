XRWebGLLayerInit.depth
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

When using the [`XRWebGLLayer()`](../xrwebgllayer/xrwebgllayer) constructor to create a new WebGL rendering layer for WebXR, providing as the `layerInit` parameter an object whose `depth` property is `false` will request that the new layer be created without a depth buffer.

Syntax
------

    let layerInit = {
      depth: false
    };
    let glLayer = new XRWebGLLayer(xrSession, gl, layerInit);

    let glLayer = new XRWebGLLayer(xrSession, gl, { depth: false });

### Value

A Boolean which can be set to `false` to specify that the new WebGL layer should not have a depth buffer. This means that the only source for depth information is the vertex coordinates, and reduces the accuracy and quality of rendering, but may potentially affect the performance of rendering as well.

The default value is `true`.

Usage notes
-----------

This property differs from [`ignoreDepthValues`](ignoredepthvalues) in that a layer created with `ignoreDepthValues` set to `true` may still have a depth buffer, but will not make use of it.

You can determine whether or not the depth buffer is being used by a given WebGL rendering layer during your XR session by checking the value returned by [`XRWebGLLayer.ignoreDepthValues`](../xrwebgllayer/ignoredepthvalues). If this is `true`, then the depth buffer is either not present or is being ignored.

    if (glLayer.ignoreDepthValues) {
      /* not using the depth buffer */
    }

Example
-------

In this example, a new [`XRWebGLLayer`](../xrwebgllayer) is created for a WebXR session, `xrSession`, without a depth buffer.

    xrSession.updateRenderState({
      baseLayer: new XRWebGLLayer(xrSession, gl, {
         depth: false
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrwebgllayerinit-depth">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayerInit.depth' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`depth`

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
-   [`XRWebGLLayer.ignoreDepthValues`](../xrwebgllayer/ignoredepthvalues)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit/depth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit/depth</a>
