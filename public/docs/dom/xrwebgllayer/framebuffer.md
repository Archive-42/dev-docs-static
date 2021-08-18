XRWebGLLayer.framebuffer
========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRWebGLLayer`](../xrwebgllayer) property `framebuffer` is an opaque [`WebGLFramebuffer`](../webglframebuffer) which is used to buffer the rendered image if the [XR compositor](../webxr_device_api/fundamentals#the_webxr_compositor) is being used. Otherwise, this property's value is `null`. The opaque framebuffer is functionally nearly the same as a standard WebGL framebuffer, except for the differences covered in the section [How opaque framebuffers are special](#how_opaque_framebuffers_are_special) below.

Syntax
------

    let framebuffer = xrWebGLLayer.framebuffer;

### Value

A [`WebGLFramebuffer`](../webglframebuffer) object representing the framebuffer into which the 3D scene is being rendered, or `null` if the [XR compositor](en-us/docs/web/api/webxr_device_api/fundamentals#The_WebXR_compositor) is disabled for the session.

Usage notes
-----------

### How opaque framebuffers are special

The framebuffer represented by the `framebuffer` property is opaque. As such, its behavior is different in several ways from a standard WebGL context. These differences cause the opaque framebuffer to behave more like the default WebGL framebuffer:

-   Opaque framebuffers *may* support [anti-aliasing](antialias), even under WebGL 1.0, which don't normally do so.
-   Opaque framebuffers' attachments (buffers and the like) can't be inspected or changed. Calling functions such as [`framebufferTexture2D()`](../webglrenderingcontext/framebuffertexture2d), [`framebufferRenderbuffer()`](../webglrenderingcontext/framebufferrenderbuffer), [`deleteFramebuffer()`](../webglrenderingcontext/deleteframebuffer), or [`getFramebufferAttachmentParameter()`](../webglrenderingcontext/getframebufferattachmentparameter) on an opaque framebuffer results in the WebGL error `INVALID_OPERATION` (0x0502).
-   Opaque framebuffers are considered incomplete and are not available for rendering other than while executing the [`requestAnimationFrame()`](../xrsession/requestanimationframe) callback. Attempting to clear, draw to, or read from the framebuffer results in a WebGL `INVALID_FRAMEBUFFER_OPERATION` error (0x0506). Calling [`checkFramebufferStatus()`](../webglrenderingcontext/checkframebufferstatus) on the WebGL context from outside the animation frame callback causes the WebGL `FRAMEBUFFER_UNSUPPORTED` error (0x8CDD) to be reported.
-   Opaque framebuffers initialized with the <span class="page-not-created">`depth`</span> property set to `false` will not have a depth buffer and will rely on the coordinates alone to determine distance.
-   Opaque framebuffers initialized without specifying a <span class="page-not-created">`stencil`</span> will not have a stencil buffer.
-   Opaque framebuffers will not have an alpha channel available unless the <span class="page-not-created">`alpha`</span> property is `true` when creating the layer.
-   The XR compositor assumes that opaque framebuffers use colors with premultiplied allpha, regardless of whether or not the WebGL context's <span class="page-not-created">`premultipliedAlpha`</span> context attribute is set.

**Note:** The `depth` and `stencil` properties are not required to be supported in order for a browser to be construed as having full WebGL support.

### The default configuration of a new framebuffer

Upon creating a new [`XRWebGLLayer`](../xrwebgllayer), its new framebuffer is initialized just like the default framebuffer for any WebGL interface:

-   The color buffer is configured with its clear value set to the color (0, 0, 0, 0) (meaning transparent black).
-   The depth buffer's clear value is the number 1.0.
-   The stencil buffer is filled with 0.

Examples
--------

This example gets the `XRWebGLLayer` for a session and then passes its framebuffer into the WebGL context's [`bindFramebuffer()`](../webglrenderingcontext/bindframebuffer) function.

    let glLayer = xrSession.renderState.baselayer;
    gl.bindFramebuffer(gl.FRAMEBUFFER, glLayer.framebuffer);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrwebgllayer-framebuffer">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayer.framebuffer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`framebuffer`

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
-   <span class="page-not-created">`WebGLContextAttributes`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer/framebuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer/framebuffer</a>
