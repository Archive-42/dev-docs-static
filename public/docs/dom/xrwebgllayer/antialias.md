XRWebGLLayer.antialias
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRWebGLLayer`](../xrwebgllayer) property `antialias` is a Boolean value which is `true` if the rendering layer's frame buffer supports antialiasing. Otherwise, this property's value is `false`. The specific antialiasing technique used is left to the [user agent's](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) discretion and cannot be specified by the web site or web app.

Syntax
------

    let antialiasingSupported = xrWebGLLayer.antialias;

### Value

A Boolean value which is `true` if the WebGL rendering layer's frame buffer is configured to support antialiasing. Otherwise, this property is `false`.

When the [WebXR compositor](../webxr_device_api/fundamentals#the_webxr_compositor) is enabled, this value corresponds to the value of the `antialias` property on the object returned by the WebGL context's [`getContentAttributes()`](../webglrenderingcontext/getcontextattributes) method.

Usage notes
-----------

Since this is a read-only property, you can set the antialiasing mode only when initially creating the `XRWebGLLayer`, by specifying the [`antialias`](../xrwebgllayerinit/antialias) object in the [`XRWebGLLayer()`](xrwebgllayer) constructor's `layerInit` parameter.

Examples
--------

This snippet checks the value of `antialias` to see if it should perform additional work to attempt to compensate for the lack of antialiasing on the WebGL layer.

    let glLayer = xrSession.renderState.baseLayer;
    gl.bindFrameBuffer(gl.FRAMEBUFFER, glLayer.framebuffer);

    /* .. */

    if (!glLayer.antialias) {
      /* compensate for lack of antialiasing */
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrwebgllayer-antialias">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayer.antialias' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`antialias`

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
-   <span class="page-not-created">`WebGLLayerInit`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer/antialias" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer/antialias</a>
