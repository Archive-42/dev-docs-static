WEBGL\_compressed\_texture\_s3tc
================================

The `WEBGL_compressed_texture_s3tc` extension is part of the [WebGL API](webgl_api) and exposes four [S3TC compressed texture formats](https://en.wikipedia.org/wiki/S3_Texture_Compression).

Compressed textures reduce the amount of memory needed to store a texture on the GPU, allowing for higher resolution textures or more of the same resolution textures.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

Constants
---------

The compressed texture formats are exposed by four constants and can be used in two functions: [`compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d) and [`compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d).

`ext.COMPRESSED_RGB_S3TC_DXT1_EXT`  
A DXT1-compressed image in an RGB image format.

`ext.COMPRESSED_RGBA_S3TC_DXT1_EXT`  
A DXT1-compressed image in an RGB image format with a simple on/off alpha value.

`ext.COMPRESSED_RGBA_S3TC_DXT3_EXT`  
A DXT3-compressed image in an RGBA image format. Compared to a 32-bit RGBA texture, it offers 4:1 compression.

`ext.COMPRESSED_RGBA_S3TC_DXT5_EXT`  
A DXT5-compressed image in an RGBA image format. It also provides a 4:1 compression, but differs to the DXT3 compression in how the alpha compression is done.

Examples
--------

    var ext = (
      gl.getExtension('WEBGL_compressed_texture_s3tc') ||
      gl.getExtension('MOZ_WEBGL_compressed_texture_s3tc') ||
      gl.getExtension('WEBKIT_WEBGL_compressed_texture_s3tc')
    );

    var texture = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, texture);

    gl.compressedTexImage2D(gl.TEXTURE_2D, 0, ext.COMPRESSED_RGBA_S3TC_DXT5_EXT, 512, 512, 0, textureData);

    gl.texParameteri(gl.TEXTURE_2D, gl.TEXTURE_MAG_FILTER, gl.LINEAR);
    gl.texParameteri(gl.TEXTURE_2D, gl.TEXTURE_MIN_FILTER, gl.LINEAR);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_compressed_texture_s3tc/">WEBGL_compressed_texture_s3tc<br />
<span class="small">The definition of 'WEBGL_compressed_texture_s3tc' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WEBGL_compressed_texture_s3tc`

26

Yes

≤18

22

15-58

11

15

Yes

8

No

No

?

No

No

No

See also
--------

-   [S3 Texture Compression – OpenGL wiki](https://www.opengl.org/wiki/S3_Texture_Compression)
-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d)
-   [`WebGLRenderingContext.compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d)
-   [`WebGLRenderingContext.getParameter()`](webglrenderingcontext/getparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_s3tc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_s3tc</a>
