WebGLRenderingContext.compressedTexSubImage2D()
===============================================

The `WebGLRenderingContext.compressedTexSubImage2D()` method of the [WebGL API](../webgl_api) specifies a two-dimensional sub-rectangle for a texture image in a compressed format.

Compressed image formats must be enabled by [WebGL extensions](../webgl_api/using_extensions) before using this method or a [`WebGL2RenderingContext`](../webgl2renderingcontext) must be used.

Syntax
------

    // WebGL 1:
    void gl.compressedTexSubImage2D(target, level, xoffset, yoffset, width, height, format, ArrayBufferView? pixels);

    // Additionally available in WebGL 2:
    void gl.compressedTexSubImage2D(target, level, xoffset, yoffset, width, height, format, imageSize, offset);
    void gl.compressedTexSubImage2D(target, level, xoffset, yoffset, width, height, format, ArrayBufferView srcData, optional srcOffset, optional srcLengthOverride);

### Parameters

`target`  
A [`GLenum`](../webgl_api/types) specifying the binding point (target) of the active compressed texture. Possible values:

-   `gl.TEXTURE_2D`: A two-dimensional texture.
-   `gl.TEXTURE_CUBE_MAP_POSITIVE_X`: Positive X face for a cube-mapped texture.
-   `gl.TEXTURE_CUBE_MAP_NEGATIVE_X`: Negative X face for a cube-mapped texture.
-   `gl.TEXTURE_CUBE_MAP_POSITIVE_Y`: Positive Y face for a cube-mapped texture.
-   `gl.TEXTURE_CUBE_MAP_NEGATIVE_Y`: Negative Y face for a cube-mapped texture.
-   `gl.TEXTURE_CUBE_MAP_POSITIVE_Z`: Positive Z face for a cube-mapped texture.
-   `gl.TEXTURE_CUBE_MAP_NEGATIVE_Z`: Negative Z face for a cube-mapped texture.

`level`  
A [`GLint`](../webgl_api/types) specifying the level of detail. Level 0 is the base image level and level *n* is the *n*th mipmap reduction level.

`xoffset`  
A [`GLint`](../webgl_api/types) specifying the horizontal offset within the compressed texture image.

`yoffset`  
A [`GLint`](../webgl_api/types) specifying the vertical offset within the compressed texture image.

`width`  
A [`GLsizei`](../webgl_api/types) specifying the width of the compressed texture.

`height`  
A [`GLsizei`](../webgl_api/types) specifying the height of the compressed texture.

`format`  
A [`GLenum`](../webgl_api/types) specifying the compressed image format. Compressed image formats must be enabled by [WebGL extensions](../webgl_api/using_extensions) before using this method. Possible values:

-   When using the [`WEBGL_compressed_texture_s3tc`](../webgl_compressed_texture_s3tc) extension:
    -   `ext.COMPRESSED_RGB_S3TC_DXT1_EXT`
    -   `ext.COMPRESSED_RGBA_S3TC_DXT1_EXT`
    -   `ext.COMPRESSED_RGBA_S3TC_DXT3_EXT`
    -   `ext.COMPRESSED_RGBA_S3TC_DXT5_EXT`
-   When using the [`WEBGL_compressed_texture_s3tc_srgb`](../webgl_compressed_texture_s3tc_srgb) extension:
    -   `ext.COMPRESSED_SRGB_S3TC_DXT1_EXT`
    -   `ext.COMPRESSED_SRGB_ALPHA_S3TC_DXT1_EXT`
    -   `ext.COMPRESSED_SRGB_ALPHA_S3TC_DXT3_EXT`
    -   `ext.COMPRESSED_SRGB_ALPHA_S3TC_DXT5_EXT`
-   When using the [`WEBGL_compressed_texture_etc`](../webgl_compressed_texture_etc) extension:
    -   `ext.COMPRESSED_R11_EAC`
    -   `ext.COMPRESSED_SIGNED_R11_EAC`
    -   `ext.COMPRESSED_RG11_EAC`
    -   `ext.COMPRESSED_SIGNED_RG11_EAC`
    -   `ext.COMPRESSED_RGB8_ETC2`
    -   `ext.COMPRESSED_RGBA8_ETC2_EAC`
    -   `ext.COMPRESSED_SRGB8_ETC2`
    -   `ext.COMPRESSED_SRGB8_ALPHA8_ETC2_EAC`
    -   `ext.COMPRESSED_RGB8_PUNCHTHROUGH_ALPHA1_ETC2`
    -   `ext.COMPRESSED_SRGB8_PUNCHTHROUGH_ALPHA1_ETC2`
-   When using the [`WEBGL_compressed_texture_pvrtc`](../webgl_compressed_texture_pvrtc) extension:
    -   `ext.COMPRESSED_RGB_PVRTC_4BPPV1_IMG`
    -   `ext.COMPRESSED_RGBA_PVRTC_4BPPV1_IMG`
    -   `ext.COMPRESSED_RGB_PVRTC_2BPPV1_IMG`
    -   `ext.COMPRESSED_RGBA_PVRTC_2BPPV1_IMG`
-   When using the [`WEBGL_compressed_texture_atc`](../webgl_compressed_texture_atc) extension:
    -   `ext.COMPRESSED_RGB_ATC_WEBGL`
    -   `ext.COMPRESSED_RGBA_ATC_EXPLICIT_ALPHA_WEBGL`
    -   `ext.COMPRESSED_RGBA_ATC_INTERPOLATED_ALPHA_WEBGL`
-   When using the [`WEBGL_compressed_texture_astc`](../webgl_compressed_texture_astc) extension:
    -   `ext.COMPRESSED_RGBA_ASTC_4x4_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_4x4_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_5x4_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_5x4_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_5x5_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_5x5_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_6x5_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_6x5_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_6x6_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_6x6_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_8x5_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_8x5_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_8x6_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_8x6_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_8x8_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_8x8_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_10x5_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_10x5_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_10x6_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_10x6_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_10x6_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_10x6_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_10x10_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_10x10_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_12x10_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_12x10_KHR`
    -   `ext.COMPRESSED_RGBA_ASTC_12x12_KHR      ext.COMPRESSED_SRGB8_ALPHA8_ASTC_12x12_KHR`
-   When using the [`EXT_texture_compression_bptc`](../ext_texture_compression_bptc) extension:
    -   `ext.COMPRESSED_RGBA_BPTC_UNORM_EXT`
    -   `ext.COMPRESSED_SRGB_ALPHA_BPTC_UNORM_EXT`
    -   `ext.COMPRESSED_RGB_BPTC_SIGNED_FLOAT_EXT`
    -   `ext.COMPRESSED_RGB_BPTC_UNSIGNED_FLOAT_EXT`
-   When using the [`EXT_texture_compression_rgtc`](../ext_texture_compression_rgtc) extension:
    -   `ext.COMPRESSED_RED_RGTC1_EXT`
    -   `ext.COMPRESSED_SIGNED_RED_RGTC1_EXT`
    -   `ext.COMPRESSED_RED_GREEN_RGTC2_EXT`
    -   `ext.COMPRESSED_SIGNED_RED_GREEN_RGTC2_EXT`

`imageSize`  
A [`GLsizei`](../webgl_api/types) specifying the number of bytes to read from the buffer bound to `gl.PIXEL_UNPACK_BUFFER`.

`offset`  
A [`GLintptr`](../webgl_api/types) specifying the offset in bytes from which to read from the buffer bound to `gl.PIXEL_UNPACK_BUFFER`.

`pixels`  
An [`ArrayBufferView`](../arraybufferview) that be used as a data store for the compressed image data in memory.

### Return value

None.

Examples
--------

    var ext = (
      gl.getExtension('WEBGL_compressed_texture_s3tc') ||
      gl.getExtension('MOZ_WEBGL_compressed_texture_s3tc') ||
      gl.getExtension('WEBKIT_WEBGL_compressed_texture_s3tc')
    );
    gl.compressedTexSubImage2D(gl.TEXTURE_2D, 0, 256, 256, 512, 512, ext.COMPRESSED_RGBA_S3TC_DXT5_EXT, textureData);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#COMPRESSEDTEXSUBIMAGE2D">WebGL 1.0<br />
<span class="small">The definition of 'compressedTexSubImage2D' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glCompressedTexSubImage2D.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glCompressedTexSubImage2D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2.0 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glCompressedTexSubImage2D.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glCompressedTexSubImage2D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`compressedTexSubImage2D`

9

12

4

11

12

5.1

≤37

25

Yes

12

8

1.5

`WebGL2`

56

79

51

No

43

No

58

58

51

43

No

7.0

See also
--------

-   [Using WebGL extensions](../webgl_api/using_extensions)
-   [`WebGLRenderingContext.getExtension()`](getextension)
-   [`WebGLRenderingContext.compressedTexImage2D()`](compressedteximage2d)
-   [`WEBGL_compressed_texture_s3tc`](../webgl_compressed_texture_s3tc)
-   [`WEBGL_compressed_texture_s3tc_srgb`](../webgl_compressed_texture_s3tc_srgb)
-   [`WEBGL_compressed_texture_etc`](../webgl_compressed_texture_etc)
-   [`WEBGL_compressed_texture_pvrtc`](../webgl_compressed_texture_pvrtc)
-   [`WEBGL_compressed_texture_atc`](../webgl_compressed_texture_atc)
-   [`WEBGL_compressed_texture_astc`](../webgl_compressed_texture_astc)
-   [`EXT_texture_compression_bptc`](../ext_texture_compression_bptc)
-   [`EXT_texture_compression_rgtc`](../ext_texture_compression_rgtc)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/compressedTexSubImage2D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/compressedTexSubImage2D</a>
