WebGLRenderingContext.compressedTexImage\[23\]D()
=================================================

The `WebGLRenderingContext.compressedTexImage2D()` and `WebGL2RenderingContext.compressedTexImage3D()` methods of the [WebGL API](../webgl_api) specify a two- or three-dimensional texture image in a compressed format.

Compressed image formats must be enabled by [WebGL extensions](../webgl_api/using_extensions) before using these methods.

Syntax
------

    // WebGL 1:
    void gl.compressedTexImage2D(target, level, internalformat, width, height, border, ArrayBufferView? pixels);

    // Additionally available in WebGL 2:
    // read from buffer bound to gl.PIXEL_UNPACK_BUFFER
    void gl.compressedTexImage2D(target, level, internalformat, width, height, border, GLsizei imageSize, GLintptr offset);
    void gl.compressedTexImage2D(target, level, internalformat, width, height, border,
                                 ArrayBufferView srcData, optional srcOffset, optional srcLengthOverride);

     // read from buffer bound to gl.PIXEL_UNPACK_BUFFER
    void gl.compressedTexImage3D(target, level, internalformat, width, height, depth, border, GLsizei imageSize, GLintptr offset);
    void gl.compressedTexImage3D(target, level, internalformat, width, height, depth, border,
                                 ArrayBufferView srcData, optional srcOffset, optional srcLengthOverride);

### Parameters

`target`  
A [`GLenum`](../webgl_api/types) specifying the binding point (target) of the active texture. Possible values for `compressedTexImage2D`:

-   `gl.TEXTURE_2D`: A two-dimensional texture.
-   `gl.TEXTURE_CUBE_MAP_POSITIVE_X`: Positive X face for a cube-mapped texture.
-   `gl.TEXTURE_CUBE_MAP_NEGATIVE_X`: Negative X face for a cube-mapped texture.
-   `gl.TEXTURE_CUBE_MAP_POSITIVE_Y`: Positive Y face for a cube-mapped texture.
-   `gl.TEXTURE_CUBE_MAP_NEGATIVE_Y`: Negative Y face for a cube-mapped texture.
-   `gl.TEXTURE_CUBE_MAP_POSITIVE_Z`: Positive Z face for a cube-mapped texture.
-   `gl.TEXTURE_CUBE_MAP_NEGATIVE_Z`: Negative Z face for a cube-mapped texture.

Possible values for `compressedTexImage3D`:

-   `gl.TEXTURE_2D_ARRAY`
-   `gl.TEXTURE_3D`

`level`  
A [`GLint`](../webgl_api/types) specifying the level of detail. Level 0 is the base image level and level *n* is the *n*th mipmap reduction level.

`internalformat`  
A [`GLenum`](../webgl_api/types) specifying the compressed image format. Compressed image formats must be enabled by [WebGL extensions](../webgl_api/using_extensions) before using this method. All values are possible for `compressedTexImage2D`. See [compressed texture formats](../webgl_api/compressed_texture_formats) for which are valid for `compressedTexImage3D`. Possible values:

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
-   When using the [`WEBGL_compressed_texture_etc1`](../webgl_compressed_texture_etc1) extension:
    -   `ext.COMPRESSED_RGB_ETC1_WEBGL`
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

`width`  
A [`GLsizei`](../webgl_api/types) specifying the width of the texture.

`height`  
A [`GLsizei`](../webgl_api/types) specifying the height of the texture.

`depth`  
A [`GLsizei`](../webgl_api/types) specifying the depth of the texture/the number of textures in a `TEXTURE_2D_ARRAY`.

`border`  
A [`GLint`](../webgl_api/types) specifying the width of the border. Must be 0.

`imageSize`  
A [`GLsizei`](../webgl_api/types) specifying the number of bytes to read from the buffer bound to `gl.PIXEL_UNPACK_BUFFER`.

`offset`  
A [`GLintptr`](../webgl_api/types) specifying the offset in bytes from which to read from the buffer bound to `gl.PIXEL_UNPACK_BUFFER`.

`pixels`  
An [`ArrayBufferView`](../arraybufferview) that will be used as a data store for the compressed image data in memory.

### Return value

None.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#COMPRESSEDTEXIMAGE2D">WebGL 1.0<br />
<span class="small">The definition of 'compressedTexImage2D' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glCompressedTexImage2D.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glCompressedTexImage2D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2.0 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glCompressedTexImage2D.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glCompressedTexImage2D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`compressedTexImage2D`

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

`SharedArrayBuffer_as_param`

60

79

79

No

47

No

60

60

?

44

No

8.0

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

`compressedTexImage2D`

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

`SharedArrayBuffer_as_param`

60

≤79

79

?

47

?

60

60

?

44

?

8.0

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

BCD tables only load in the browser

### compressedTexImage3D

BCD tables only load in the browser

See also
--------

-   [Using WebGL extensions](../webgl_api/using_extensions)
-   [`WebGLRenderingContext.compressedTexSubImage2D()`](compressedtexsubimage2d)
-   [`WEBGL_compressed_texture_s3tc`](../webgl_compressed_texture_s3tc)
-   [`WEBGL_compressed_texture_s3tc_srgb`](../webgl_compressed_texture_s3tc_srgb)
-   [`WEBGL_compressed_texture_etc`](../webgl_compressed_texture_etc)
-   [`WEBGL_compressed_texture_pvrtc`](../webgl_compressed_texture_pvrtc)
-   [`WEBGL_compressed_texture_etc1`](../webgl_compressed_texture_etc1)
-   [`WEBGL_compressed_texture_atc`](../webgl_compressed_texture_atc)
-   [`WEBGL_compressed_texture_astc`](../webgl_compressed_texture_astc)
-   [`EXT_texture_compression_bptc`](../ext_texture_compression_bptc)
-   [`EXT_texture_compression_rgtc`](../ext_texture_compression_rgtc)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/compressedTexImage2D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/compressedTexImage2D</a>
