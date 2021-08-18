WEBGL\_debug\_renderer\_info
============================

The `WEBGL_debug_renderer_info` extension is part of the [WebGL API](webgl_api) and exposes two constants with information about the graphics driver for debugging purposes.

Depending on the privacy settings of the browser, this extension might only be available to privileged contexts. Generally, the graphics driver information should only be used in edge cases to optimize your WebGL content or to debug GPU problems. The [`WebGLRenderingContext.getParameter()`](webglrenderingcontext/getparameter) method can help you to detect which features are supported and the `failIfMajorPerformanceCaveat` context attribute lets you control if a context should be returned at all, if the performance would be dramatically slow.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** Depending on the privacy settings of the browser, this extension might only be available to privileged contexts or not work at all. In Firefox, if `privacy.resistFingerprinting` is set to `true`, this extensions is disabled.

This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

Constants
---------

ext.UNMASKED\_VENDOR\_WEBGL  
Vendor string of the graphics driver.

ext.UNMASKED\_RENDERER\_WEBGL  
Renderer string of the graphics driver.

Examples
--------

With the help of this extension, privileged contexts are able to retrieve debugging information about the user's graphic driver:

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');

    var debugInfo = gl.getExtension('WEBGL_debug_renderer_info');
    var vendor = gl.getParameter(debugInfo.UNMASKED_VENDOR_WEBGL);
    var renderer = gl.getParameter(debugInfo.UNMASKED_RENDERER_WEBGL);

    console.log(vendor);
    console.log(renderer);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_debug_renderer_info/">WEBGL_debug_renderer_info<br />
<span class="small">The definition of 'WEBGL_debug_renderer_info' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WEBGL_debug_renderer_info`

33

≤18

53

11

Yes

9.1

37

33

?

?

9.3

2.0

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_debug_renderer_info" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_debug_renderer_info</a>
