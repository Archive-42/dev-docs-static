XRWebGLLayerInit.alpha
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `alpha` property is a Boolean value which, if present and set to `true` in the [`XRWebGLLayerInit`](../xrwebgllayerinit) dictionary passed into the [`XRWebGLLayer()`](../xrwebgllayer/xrwebgllayer) constructor, specifies that the new layer's color buffer is to include an [alpha channel](https://developer.mozilla.org/en-US/docs/Glossary/Alpha). Otherwise, the color buffer won't have an alpha channel. The default is `true`.

Syntax
------

    let layerInit = {
      alpha: boolValue
    };
    let glLayer = new XRWebGLLayer(xrSession, gl, layerInit);

    let glLayer = new XRWebGLLayer(xrSession, gl, { alpha: boolValue });

### Value

A Boolean which can be set to `true` to request that the new WebGL layer for rendering the WebXR scene is to have an alpha channel.

Example
-------

In this example, a new [`XRWebGLLayer`](../xrwebgllayer) is created for a WebXR session, `xrSession`, without an alpha channel.

    xrSession.updateRenderState({
      baseLayer: new XRWebGLLayer(xrSession, gl, {
         alpha: false
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrwebgllayerinit-alpha">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayerInit.alpha' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`alpha`

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
-   [`WebGLRenderingContext`](../webglrenderingcontext) and [`WebGL2RenderingContext`](../webgl2renderingcontext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit/alpha" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit/alpha</a>
