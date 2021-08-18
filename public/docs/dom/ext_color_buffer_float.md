# EXT_color_buffer_float

The `EXT_color_buffer_float` extension is part of [WebGL](webgl_api) and adds the ability to render a variety of floating point formats.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is available to [WebGL 2](webgl2renderingcontext) contexts only.

For [WebGL 1](webglrenderingcontext), see the [`EXT_color_buffer_half_float`](ext_color_buffer_half_float) and [`WEBGL_color_buffer_float`](webgl_color_buffer_float) extensions.

## Extended methods

The following sized formats become **color-renderable**:

- `gl.R16F`,
- `gl.RG16F`,
- `gl.RGBA16F`,
- `gl.R32F`,
- `gl.RG32F`,
- `gl.RGBA32F`,
- `gl.R11F_G11F_B10F`.

**Color-renderable** means:

- The [`WebGLRenderingContext.renderbufferStorage()`](webglrenderingcontext/renderbufferstorage) method now accepts these formats.
- Framebuffers with attached textures of these formats may now be **FRAMEBUFFER_COMPLETE**.

## Examples

`gl` must be a [`WebGL2RenderingContext`](webgl2renderingcontext). This extension does not work in WebGL 1 contexts.

    var ext = gl.getExtension('EXT_color_buffer_float');

    gl.renderbufferStorage(gl.RENDERBUFFER, gl.RGBA16F, 256, 256);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_color_buffer_float/">EXT_color_buffer_float<br />
<span class="small">The definition of 'EXT_color_buffer_float' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr></tbody></table>

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

`EXT_color_buffer_float`

63

79

49

No

?

No

63

63

?

?

No

8.0

## See also

- [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
- [`WebGLRenderingContext.renderbufferStorage()`](webglrenderingcontext/renderbufferstorage)
- [`EXT_color_buffer_half_float`](ext_color_buffer_half_float)
- [`WEBGL_color_buffer_float`](webgl_color_buffer_float)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_color_buffer_float" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_color_buffer_float</a>
