WEBGL\_compressed\_texture\_etc1
================================

The `WEBGL_compressed_texture_etc1` extension is part of the [WebGL API](webgl_api) and exposes the [ETC1 compressed texture format](https://en.wikipedia.org/wiki/Ericsson_Texture_Compression).

Compressed textures reduce the amount of memory needed to store a texture on the GPU, allowing for higher resolution textures or more of the same resolution textures.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

Constants
---------

The compressed texture format is exposed by a constant and can be used with the [`compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d) method (note that ETC1 is **not** supported with the [`compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d) method).

`ext.COMPRESSED_RGB_ETC1_WEBGL`  
Compresses 24-bit RGB data with no alpha channel.

Examples
--------

    var ext = gl.getExtension('WEBGL_compressed_texture_etc1');

    var texture = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, texture);

    gl.compressedTexImage2D(gl.TEXTURE_2D, 0, ext.COMPRESSED_RGB_ETC1_WEBGL, 512, 512, 0, textureData);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_compressed_texture_etc1/">WEBGL_compressed_texture_etc1<br />
<span class="small">The definition of 'WEBGL_compressed_texture_etc1' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WEBGL_compressed_texture_etc1`

49

79

30

No

36

No

49

49

?

36

No

5.0

See also
--------

-   [Ericsson Texture Compression – Wikipedia](https://en.wikipedia.org/wiki/Ericsson_Texture_Compression)
-   [`WEBGL_compressed_texture_es3`](webgl_compressed_texture_etc) (ETC2 and EAC)
-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d)
-   [`WebGLRenderingContext.getParameter()`](webglrenderingcontext/getparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_etc1" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_etc1</a>
