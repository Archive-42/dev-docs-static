XRWebGLLayer.framebufferWidth
=============================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRWebGLLayer`](../xrwebgllayer) property `framebufferWidth` specifies the width of the framebuffer, in pixels.

You can get the height of the framebuffer using the [`framebufferHeight`](framebufferheight) property.

Syntax
------

    let bufferWidth = xrWebGLLayer.framebufferWidth;

### Value

The width in pixels of the XR device's framebuffer. Each of the framebuffer's attachments (pixel, depth, color, and/or stencil buffers, for example) are all this many pixels wide.

Examples
--------

This snippet fetches the framebuffer's width and height for later use.

    let glLayer = xrSession.renderState.baseLayer;
    gl.bindFramebuffer(gl.FRAMEBUFFER, glLayer.framebuffer);

    frameWidth = glLayer.framebufferWidth;
    frameHeight = glLayer.framebufferHeight;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrwebgllayer-framebufferwidth">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayer.framebufferWidth' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`framebufferWidth`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer/framebufferWidth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer/framebufferWidth</a>
