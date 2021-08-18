WEBGL\_compressed\_texture\_pvrtc
=================================

The `WEBGL_compressed_texture_pvrtc` extension is part of the [WebGL API](webgl_api) and exposes four [PVRTC compressed texture formats](https://en.wikipedia.org/wiki/PVRTC).

Compressed textures reduce the amount of memory needed to store a texture on the GPU, allowing for higher resolution textures or more of the same resolution textures.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** PVRTC is typically only available on mobile devices with PowerVR chipsets. It is used in all generations of the iPhone, iPod Touch and iPad and supported on certain Android devices that use a PowerVR GPU.

This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

**Note**: On iOS devices, this extension is named `WEBKIT_WEBGL_compressed_texture_pvrtc`.

Constants
---------

The compressed texture formats are exposed by four constants and can be used in two functions: [`compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d) (where the `height` and `width` parameters must be powers of 2) and [`compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d) (where the height and width parameters must equal the current values of the existing texture and the `xoffset` and `yoffset` parameters must be 0).

`ext.COMPRESSED_RGB_PVRTC_4BPPV1_IMG`  
RGB compression in 4-bit mode. One block for each 4×4 pixels.

`ext.COMPRESSED_RGBA_PVRTC_4BPPV1_IMG`  
RGBA compression in 4-bit mode. One block for each 4×4 pixels.

`ext.COMPRESSED_RGB_PVRTC_2BPPV1_IMG`  
RGB compression in 2-bit mode. One block for each 8×4 pixels.

`ext.COMPRESSED_RGBA_PVRTC_2BPPV1_IMG`  
RGBA compression in 2-bit mode. One block for each 8×4 pixels.

Examples
--------

    var ext = gl.getExtension('WEBGL_compressed_texture_pvrtc');

    var texture = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, texture);

    gl.compressedTexImage2D(gl.TEXTURE_2D, 0, ext.COMPRESSED_RGB_PVRTC_4BPPV1_IMG, 512, 512, 0, textureData);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_compressed_texture_pvrtc/">WEBGL_compressed_texture_pvrtc<br />
<span class="small">The definition of 'WEBGL_compressed_texture_pvrtc' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WEBGL_compressed_texture_pvrtc`

Yes

79

18

Yes-58

No

Yes

No

Yes

Yes

?

Yes

No

Yes

See also
--------

-   [PVRTC Texture Compression – Wikipedia](https://en.wikipedia.org/wiki/PVRTC)
-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d)
-   [`WebGLRenderingContext.compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d)
-   [`WebGLRenderingContext.getParameter()`](webglrenderingcontext/getparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_pvrtc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_pvrtc</a>
