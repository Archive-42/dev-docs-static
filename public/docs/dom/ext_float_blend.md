# EXT_float_blend

The [WebGL API](webgl_api)'s `EXT_float_blend` extension allows blending and draw buffers with 32-bit floating-point components.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts. However, to use it, you need to enable the use of 32-bit floating-point draw buffers by enabling the extension [`WEBGL_color_buffer_float`](webgl_color_buffer_float) (for WebGL1) or [`EXT_color_buffer_float`](ext_color_buffer_float) (for WebGL2). Doing so automatically enables `EXT_float_blend` as well.

With this extension enabled, calling [`drawArrays()`](webglrenderingcontext/drawarrays) or [`drawElements()`](webglrenderingcontext/drawelements) with blending enabled and a draw buffer with 32-bit floating-point components will no longer result in an `INVALID_OPERATION` error.

## Usage notes

On devices that support the `EXT_float_blend` extension, it is automatically, implicitly, enabled when any one or more of [`EXT_color_buffer_float`](ext_color_buffer_float), [`OES_texture_float`](oes_texture_float), or [`WEBGL_color_buffer_float`](webgl_color_buffer_float) are enabled. This ensures that content written before `EXT_float_blend` was exposed by WebGL will function as expected.

## Examples

    const gl = canvas.getContext('webgl2');

    // enable necessary extensions
    gl.getExtension('EXT_color_buffer_float');
    gl.getExtension('EXT_float_blend');

    const tex = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, tex);

    // use floating point format
    gl.texImage2D(gl.TEXTURE_2D, 0, gl.RGBA32F, 1, 1, 0, gl.RGBA, gl.FLOAT, null);

    const fb = gl.createFramebuffer();
    gl.bindFramebuffer(gl.FRAMEBUFFER, fb);
    gl.framebufferTexture2D(gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_2D, tex, 0);

    // enable blending
    gl.enable(gl.BLEND);

    gl.drawArrays(gl.POINTS, 0, 1);
    // won't throw gl.INVALID_OPERATION with the extension enabled

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_float_blend/">EXT_float_blend</a></td><td>Draft</td></tr></tbody></table>

## Browser compatibility

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

`EXT_float_blend`

75

79

67

No

No

14.1

No

75

Until Chrome 77, this extension was unavailable on several Android devices powered by GLES 3.2. See [bug 964208](https://crbug.com/964208).

No

No

No

No

## See also

- [WebGL API](webgl_api)
- [Using WebGL extensions](webgl_api/using_extensions)
- [WebGL tutorial](webgl_api/tutorial)
- [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
- [`EXT_color_buffer_float`](ext_color_buffer_float)
- [`WEBGL_color_buffer_float`](webgl_color_buffer_float)
- [`WebGLRenderingContext.drawArrays()`](webglrenderingcontext/drawarrays)
- [`WebGLRenderingContext.drawElements()`](webglrenderingcontext/drawelements)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_float_blend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_float_blend</a>
