# EXT_sRGB

The `EXT_sRGB` extension is part of the [WebGL API](webgl_api) and adds sRGB support to textures and framebuffer objects.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is only available to [WebGL1](webglrenderingcontext) contexts. In [WebGL2](webgl2renderingcontext), the functionality of this extension is available on the WebGL2 context by default. The constants in WebGL2 are: `gl.SRGB`, `gl.SRGB8`, `gl.SRGB8_ALPHA8` and `gl.FRAMEBUFFER_ATTACHMENT_COLOR_ENCODING`.

## Constants

This extension exposes the following constants, which can be used in the [`texImage2D()`](webglrenderingcontext/teximage2d), [`texSubImage2D()`](webglrenderingcontext/texsubimage2d), [`renderbufferStorage()`](webglrenderingcontext/renderbufferstorage) and [`getFramebufferAttachmentParameter()`](webglrenderingcontext/getframebufferattachmentparameter) methods.

`ext.SRGB_EXT`  
Unsized sRGB format that leaves the precision up to the driver.

`ext.SRGB_ALPHA_EXT`  
Unsized sRGB format with unsized alpha component.

`ext.SRGB8_ALPHA8_EXT`  
Sized (8-bit) sRGB and alpha formats.

`ext.FRAMEBUFFER_ATTACHMENT_COLOR_ENCODING_EXT`  
Returns the framebuffer color encoding (`gl.LINEAR` or `ext.SRGB_EXT`).

## Examples

    var ext = gl.getExtension('EXT_sRGB');

    var texture = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, texture);

    gl.texImage2D(gl.TEXTURE_2D, 0, ext.SRGB_EXT, 512, 512, 0,
                  ext.SRGB_EXT, gl.UNSIGNED_BYTE, image);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_sRGB/">EXT_sRGB<br />
<span class="small">The definition of 'EXT_sRGB' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`EXT_sRGB`

40

No

58

28-58

Not supported on Windows.

No

27

7

40

40

?

27

9

4.0

## See also

- [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
- [`WebGLRenderingContext.texImage2D()`](webglrenderingcontext/teximage2d)
- [`WebGLRenderingContext.texSubImage2D()`](webglrenderingcontext/texsubimage2d)
- [`WebGLRenderingContext.renderbufferStorage()`](webglrenderingcontext/renderbufferstorage)
- [`WebGLRenderingContext.getFramebufferAttachmentParameter()`](webglrenderingcontext/getframebufferattachmentparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_sRGB" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_sRGB</a>
