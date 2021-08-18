WEBGL\_color\_buffer\_float
===========================

The `WEBGL_color_buffer_float` extension is part of the [WebGL API](webgl_api) and adds the ability to render to 32-bit floating-point color buffers.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is available to [WebGL 1](webglrenderingcontext) contexts only. For [WebGL 2](webgl2renderingcontext), use the [`EXT_color_buffer_float`](ext_color_buffer_float) extension.

The [`OES_texture_float`](oes_texture_float) extension implicitly enables this extension.

Constants
---------

`ext.RGBA32F_EXT`  
RGBA 32-bit floating-point color-renderable format.

 `ext.RGB32F_EXT` (<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>)  
RGB 32-bit floating-point color-renderable format.

`ext.FRAMEBUFFER_ATTACHMENT_COMPONENT_TYPE_EXT`  
?

`ext.UNSIGNED_NORMALIZED_EXT`  
?

Extended methods
----------------

This extension extends [`WebGLRenderingContext.renderbufferStorage()`](webglrenderingcontext/renderbufferstorage):

-   The `internalformat` parameter now accepts `ext.RGBA32F_EXT` and `ext.RGB32F_EXT` (<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>).

Examples
--------

    var ext = gl.getExtension('WEBGL_color_buffer_float');

    gl.renderbufferStorage(gl.RENDERBUFFER, ext.RGBA32F_EXT, 256, 256);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_color_buffer_float/">WEBGL_color_buffer_float<br />
<span class="small">The definition of 'WEBGL_color_buffer_float' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WEBGL_color_buffer_float`

63

17

30

No

50

14

63

63

?

46

No

8.0

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.renderbufferStorage()`](webglrenderingcontext/renderbufferstorage)
-   [`OES_texture_float`](oes_texture_float)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_color_buffer_float" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_color_buffer_float</a>
