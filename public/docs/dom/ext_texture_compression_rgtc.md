EXT\_texture\_compression\_rgtc
===============================

The `EXT_texture_compression_rgtc` extension is part of the [WebGL API](webgl_api) and exposes 4 RGTC compressed texture formats. RGTC is a block-based texture compression format suited for unsigned and signed red and red-green textures (**R**ed-**G**reen **T**exture **C**ompression).

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** Support depends on the system's graphics driver. There is no support on Windows.

This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

Constants
---------

The compressed texture formats are exposed by 4 constants and can be used in two functions: [`compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d) and [`compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d).

`ext.COMPRESSED_RED_RGTC1_EXT`  
Each 4x4 block of texels consists of 64 bits of unsigned red image data. See also [BC4 unsigned](https://docs.microsoft.com/en-us/windows/desktop/direct3d10/d3d10-graphics-programming-guide-resources-block-compression#bc4).

`ext.COMPRESSED_SIGNED_RED_RGTC1_EXT`  
Each 4x4 block of texels consists of 64 bits of signed red image data. See also [BC4 signed](https://docs.microsoft.com/en-us/windows/desktop/direct3d10/d3d10-graphics-programming-guide-resources-block-compression#bc4).

`ext.COMPRESSED_RED_GREEN_RGTC2_EXT`  
Each 4x4 block of texels consists of 64 bits of compressed unsigned red image data followed by 64 bits of compressed unsigned green image data. See also [BC5 unsigned](https://docs.microsoft.com/en-us/windows/desktop/direct3d10/d3d10-graphics-programming-guide-resources-block-compression#bc5).

`ext.COMPRESSED_SIGNED_RED_GREEN_RGTC2_EXT`  
Each 4x4 block of texels consists of 64 bits of compressed signed red image data followed by 64 bits of compressed signed green image data. See also [BC5 signed](https://docs.microsoft.com/en-us/windows/desktop/direct3d10/d3d10-graphics-programming-guide-resources-block-compression#bc5).

Examples
--------

    var ext = gl.getExtension('EXT_texture_compression_rgtc');

    var texture = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, texture);

    gl.compressedTexImage2D(gl.TEXTURE_2D, 0, ext.COMPRESSED_RED_RGTC1_EXT, 128, 128, 0, textureData);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_texture_compression_rgtc/">EXT_texture_compression_rgtc</a></td><td>Community Approved</td></tr></tbody></table>

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

`EXT_texture_compression_rgtc`

No

No

65

Only supported on macOS.

No

No

14.1

No

No

No

No

No

No

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d)
-   [`WebGLRenderingContext.compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d)
-   [`WebGLRenderingContext.getParameter()`](webglrenderingcontext/getparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_texture_compression_rgtc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_texture_compression_rgtc</a>
