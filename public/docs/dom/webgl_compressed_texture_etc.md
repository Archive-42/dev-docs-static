WEBGL\_compressed\_texture\_etc
===============================

The `WEBGL_compressed_texture_etc` extension is part of the [WebGL API](webgl_api) and exposes 10 [ETC/EAC compressed texture formats](https://en.wikipedia.org/wiki/Ericsson_Texture_Compression).

Compressed textures reduce the amount of memory needed to store a texture on the GPU, allowing for higher resolution textures or more of the same resolution textures.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

Constants
---------

The compressed texture formats are exposed by 10 constants and can be used in two functions: [`compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d) and [`compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d).

`ext.COMPRESSED_R11_EAC`  
One-channel (red) unsigned format compression.

`ext.COMPRESSED_SIGNED_R11_EAC`  
One-channel (red) signed format compression.

`ext.COMPRESSED_RG11_EAC`  
Two-channel (red and green) unsigned format compression.

`ext.COMPRESSED_SIGNED_RG11_EAC`  
Two-channel (red and green) signed format compression.

`ext.COMPRESSED_RGB8_ETC2`  
Compresses RGB8 data with no alpha channel.

`ext.COMPRESSED_RGBA8_ETC2_EAC`  
Compresses RGBA8 data. The RGB part is encoded the same as `RGB_ETC2`, but the alpha part is encoded separately.

`ext.COMPRESSED_SRGB8_ETC2`  
Compresses sRGB8 data with no alpha channel.

`ext.COMPRESSED_SRGB8_ALPHA8_ETC2_EAC`  
Compresses sRGBA8 data. The sRGB part is encoded the same as `SRGB_ETC2`, but the alpha part is encoded separately.

`ext.COMPRESSED_RGB8_PUNCHTHROUGH_ALPHA1_ETC2`  
Similar to `RGB8_ETC`, but with ability to punch through the alpha channel, which means to make it completely opaque or transparent.

`ext.COMPRESSED_SRGB8_PUNCHTHROUGH_ALPHA1_ETC2`  
Similar to `SRGB8_ETC`, but with ability to punch through the alpha channel, which means to make it completely opaque or transparent.

Examples
--------

    var ext = gl.getExtension('WEBGL_compressed_texture_etc');

    var texture = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, texture);

    gl.compressedTexImage2D(gl.TEXTURE_2D, 0, ext.COMPRESSED_RGBA8_ETC2_EAC, 512, 512, 0, textureData);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_compressed_texture_etc/">WEBGL_compressed_texture_etc<br />
<span class="small">The definition of 'WEBGL_compressed_texture_etc' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WEBGL_compressed_texture_etc`

63

79

51

No

50

No

63

63

?

46

14

8.0

Compatibility notes
-------------------

-   This extension was named `WEBGL_compressed_texture_es3` from Firefox 46 to Firefox 51 and used to be available on the WebGL 2 context by default – this is not the case anymore. You have to enable it on both, WebGL 1 and WebGL 2 contexts, in order to use it.

See also
--------

-   [Ericsson Texture Compression – Wikipedia](https://en.wikipedia.org/wiki/Ericsson_Texture_Compression)
-   [`WEBGL_compressed_texture_etc1`](webgl_compressed_texture_etc1) (ETC1)
-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d)
-   [`WebGLRenderingContext.compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d)
-   [`WebGLRenderingContext.getParameter()`](webglrenderingcontext/getparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_etc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_etc</a>
