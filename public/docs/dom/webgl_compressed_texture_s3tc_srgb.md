WEBGL\_compressed\_texture\_s3tc\_srgb
======================================

The `WEBGL_compressed_texture_s3tc_srgb` extension is part of the [WebGL API](webgl_api) and exposes four [S3TC compressed texture formats](https://en.wikipedia.org/wiki/S3_Texture_Compression) for the sRGB colorspace.

Compressed textures reduce the amount of memory needed to store a texture on the GPU, allowing for higher resolution textures or more of the same resolution textures.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is available to both [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

Constants
---------

The compressed texture formats are exposed by four constants and can be used in two functions: [`compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d) and [`compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d).

`ext.COMPRESSED_SRGB_S3TC_DXT1_EXT`  
A DXT1-compressed image in an sRGB image format.

`ext.COMPRESSED_SRGB_ALPHA_S3TC_DXT1_EXT`  
A DXT1-compressed image in an sRGB image format with a simple on/off alpha value.

`ext.COMPRESSED_SRGB_ALPHA_S3TC_DXT3_EXT`  
A DXT3-compressed image in an sRGBA image format.

`ext.COMPRESSED_SRGB_ALPHA_S3TC_DXT5_EXT`  
A DXT5-compressed image in an sRGBA image format.

Examples
--------

    var ext = gl.getExtension('WEBGL_compressed_texture_s3tc_srgb');

    var texture = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, texture);

    gl.compressedTexImage2D(gl.TEXTURE_2D, 0, ext.COMPRESSED_SRGB_S3TC_DXT1_EXT, 512, 512, 0, textureData);

    gl.texParameteri(gl.TEXTURE_2D, gl.TEXTURE_MAG_FILTER, gl.LINEAR);
    gl.texParameteri(gl.TEXTURE_2D, gl.TEXTURE_MIN_FILTER, gl.LINEAR);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_compressed_texture_s3tc_srgb/">WEBGL_compressed_texture_s3tc_srgb<br />
<span class="small">The definition of 'WEBGL_compressed_texture_s3tc_srgb' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WEBGL_compressed_texture_s3tc_srgb`

60

≤79

55

No

47

No

60

60

?

44

No

8.0

See also
--------

-   [S3 Texture Compression – OpenGL wiki](https://www.khronos.org/opengl/wiki/S3_Texture_Compression#sRGB_and_S3TC)
-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d)
-   [`WebGLRenderingContext.compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d)
-   [`WebGLRenderingContext.getParameter()`](webglrenderingcontext/getparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_s3tc_srgb" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_s3tc_srgb</a>
