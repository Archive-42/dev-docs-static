# EXT_color_buffer_half_float

The `EXT_color_buffer_half_float` extension is part of the [WebGL API](webgl_api) and adds the ability to render to 16-bit floating-point color buffers.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts. On WebGL 2, it's an alternative to using the [`EXT_color_buffer_float`](ext_color_buffer_float) extension on platforms that support 16-bit floating point render targets but not 32-bit floating point render targets.

The [`OES_texture_half_float`](oes_texture_half_float) extension implicitly enables this extension.

## Constants

`ext.RGBA16F_EXT`  
RGBA 16-bit floating-point color-renderable format.

`ext.RGB16F_EXT`  
RGB 16-bit floating-point color-renderable format.

`ext.FRAMEBUFFER_ATTACHMENT_COMPONENT_TYPE_EXT`  
?

`ext.UNSIGNED_NORMALIZED_EXT`  
?

## Extended methods

This extension extends [`WebGLRenderingContext.renderbufferStorage()`](webglrenderingcontext/renderbufferstorage):

- The `internalformat` parameter now accepts `ext.RGBA16F_EXT` and `ext.RGBA16F_EXT`.

## Examples

    var ext = gl.getExtension('EXT_color_buffer_half_float');

    gl.renderbufferStorage(gl.RENDERBUFFER, ext.RBGA16F_EXT, 256, 256);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_color_buffer_half_float/">EXT_color_buffer_half_float<br />
<span class="small">The definition of 'EXT_color_buffer_half_float' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`EXT_color_buffer_half_float`

63

17

47

36-47

Not supported on Windows.

No

50

14

63

63

?

46

14

8.0

## See also

- [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
- [`WebGLRenderingContext.renderbufferStorage()`](webglrenderingcontext/renderbufferstorage)
- [`OES_texture_half_float`](oes_texture_half_float)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_color_buffer_half_float" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_color_buffer_half_float</a>
