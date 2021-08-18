EXT\_texture\_norm16
====================

The `EXT_texture_norm16` extension is part of the [WebGL API](webgl_api) and provides a set of new 16-bit signed normalized and unsigned normalized formats (fixed-point texture, renderbuffer and texture buffer).

When this extension is enabled:

-   The [`WebGLRenderingContext.texImage2D()`](webglrenderingcontext/teximage2d) and [`WebGLRenderingContext.texSubImage2D()`](webglrenderingcontext/texsubimage2d) methods accept new formats provided by this extension.
-   The 16-bit normalized fixed-point types `ext.R16_EXT`, `ext.RG16_EXT` and `ext.RGBA16_EXT` become available as color-renderable formats and renderbuffers and be created in these formats.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is only available to [WebGL 2](webgl2renderingcontext) contexts.

Constants
---------

`ext.R16_EXT`  
Red 16-bit unsigned format. Color-renderable.

`ext.RG16_EXT`  
RG 16-bit unsigned format. Color-renderable.

`ext.RGB16_EXT`  
RGB 16-bit unsigned format.

`ext.RGBA16_EXT`  
RGBA 16-bit unsigned format. Color-renderable.

`ext.R16_SNORM_EXT`  
Red 16-bit signed normalized format.

`ext.RG16_SNORM__EXT`  
RG 16-bit signed normalized format.

`ext.RGB16_SNORM__EXT`  
RGB 16-bit signed normalized format.

`ext.RGBA16_SNORM__EXT`  
RGBA 16-bit signed normalized format.

Examples
--------

### Enabling the extension

    let ext = gl.getExtension('EXT_texture_norm16');

### Texture formats

The [`WebGLRenderingContext.texImage2D()`](webglrenderingcontext/teximage2d) method accepts new formats when `EXT_texture_norm16` is enabled. Example calls:

    // imageData = Uint16Array
    gl.texImage2D(gl.TEXTURE_2D, 0, ext.R16_EXT, 1, 1, 0, gl.RED, gl.UNSIGNED_SHORT, imageData);
    gl.texImage2D(gl.TEXTURE_2D, 0, ext.RG16_EXT, 1, 1, 0, gl.RG, gl.UNSIGNED_SHORT, imageData);
    gl.texImage2D(gl.TEXTURE_2D, 0, ext.RGB16_EXT, 1, 1, 0, gl.RGB, gl.UNSIGNED_SHORT, imageData);
    gl.texImage2D(gl.TEXTURE_2D, 0, ext.RGBA16_EXT, 1, 1, 0, gl.RGBA, gl.UNSIGNED_SHORT, imageData);

    // imageData = Int16Array
    gl.texImage2D(gl.TEXTURE_2D, 0, ext.R16_SNORM_EXT, 1, 1, 0, gl.RED, gl.SHORT, imageData);
    gl.texImage2D(gl.TEXTURE_2D, 0, ext.RG16_SNORM_EXT, 1, 1, 0, gl.RG, gl.SHORT, imageData);
    gl.texImage2D(gl.TEXTURE_2D, 0, ext.RGB16_SNORM_EXT, 1, 1, 0, gl.RGB, gl.SHORT, imageData);
    gl.texImage2D(gl.TEXTURE_2D, 0, ext.RGBA16_SNORM_EXT, 1, 1, 0, gl.RGBA, gl.SHORT, imageData);

### Renderbuffer formats

The [`WebGLRenderingContext.renderbufferStorage()`](webglrenderingcontext/renderbufferstorage) method accepts `ext.R16_EXT`, `ext.RG16_EXT` and `ext.RGBA16_EXT` as internal formats to create renderbuffers in these formats. Example calls:

    gl.renderbufferStorage(gl.RENDERBUFFER, ext.R16_EXT, 1, 1);
    gl.renderbufferStorage(gl.RENDERBUFFER, ext.RG16_EXT, 1, 1);
    gl.renderbufferStorage(gl.RENDERBUFFER, ext.RGBA16_EXT, 1, 1);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_texture_norm16/">EXT_texture_norm16<br />
<span class="small">The definition of 'EXT_texture_norm16' in that specification.</span></a></td></tr></tbody></table>

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

`EXT_texture_norm16`

87

No

No

No

No

No

87

87

No

No

No

14.0

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.texImage2D()`](webglrenderingcontext/teximage2d)
-   [`WebGLRenderingContext.renderbufferStorage()`](webglrenderingcontext/renderbufferstorage)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_texture_norm16" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_texture_norm16</a>
