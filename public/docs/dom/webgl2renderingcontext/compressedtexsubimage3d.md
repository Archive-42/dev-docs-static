WebGL2RenderingContext.compressedTexSubImage3D()
================================================

The `WebGL2RenderingContext.compressedTexSubImage3D()` method of the [WebGL API](../webgl_api) specifies a three-dimensional sub-rectangle for a texture image in a compressed format.

Syntax
------

    // read from the buffer bound to gl.PIXEL_UNPACK_BUFFER
    void gl.compressedTexSubImage3D(target, level, xoffset, yoffset, zoffset, width, height, depth, format, imageSize, offset);

    void gl.compressedTexSubImage3D(target, level, xoffset, yoffset, zoffset, width, height, depth, format, ArrayBufferView srcData, optional srcOffset, optional srcLengthOverride);

### Parameters

`target`  
A [`GLenum`](../webgl_api/types) specifying the binding point (target) of the active texture. Possible values:

-   `gl.TEXTURE_3D`: A three-dimensional texture.
-   `gl.TEXTURE_2D_ARRAY`: A two-dimensional array texture.

`level`  
A [`GLint`](../webgl_api/types) specifying the level of detail. Level 0 is the base image level and level *n* is the *n*th mipmap reduction level.

`xoffset`  
A [`GLint`](../webgl_api/types) specifying the x offset within the compressed texture image.

`yoffset`  
A [`GLint`](../webgl_api/types) specifying the y offset within the compressed texture image.

`zoffset`  
A [`GLint`](../webgl_api/types) specifying the z offset within the compressed texture image.

`width`  
A [`GLsizei`](../webgl_api/types) specifying the width of the texture.

`height`  
A [`GLsizei`](../webgl_api/types) specifying the height of the texture.

`depth`  
A [`GLsizei`](../webgl_api/types) specifying the depth of the texture.

`format`  
A [`GLenum`](../webgl_api/types) specifying the compressed image format. Possible values:

-   `gl.COMPRESSED_R11_EAC`
-   `gl.COMPRESSED_SIGNED_R11_EAC`
-   `gl.COMPRESSED_RG11_EAC`
-   `gl.COMPRESSED_SIGNED_RG11_EAC`
-   `gl.COMPRESSED_RGB8_ETC2`
-   `gl.COMPRESSED_RGBA8_ETC2_EAC`
-   `gl.COMPRESSED_SRGB8_ETC2`
-   `gl.COMPRESSED_SRGB8_ALPHA8_ETC2_EAC`
-   `gl.COMPRESSED_RGB8_PUNCHTHROUGH_ALPHA1_ETC2`
-   `gl.COMPRESSED_SRGB8_PUNCHTHROUGH_ALPHA1_ETC2`

`imageSize`  
A [`GLint`](../webgl_api/types) specifying the number of bytes to read from the buffer bound to `gl.PIXEL_UNPACK_BUFFER`.

`offset`  
A [`GLint`](../webgl_api/types) specifying the offset in bytes from which to read from the buffer bound to `gl.PIXEL_UNPACK_BUFFER`.

`srcData`  
An [`ArrayBufferView`](../arraybufferview) that be used as a data store for the compressed image data in memory.

### Return value

None.

Examples
--------

    gl.compressedTexSubImage3D(gl.TEXTURE_3D, 0, 0, 0, 512, 512, 512, gl.COMPRESSED_R11_EAC, textureData);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.6">WebGL 2.0<br />
<span class="small">The definition of 'compressedTexSubImage3D' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glCompressedTexSubImage3D.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glCompressedTexSubImage3D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`compressedTexSubImage3D`

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

-   [`WebGLRenderingContext.compressedTexSubImage2D()`](../webglrenderingcontext/compressedtexsubimage2d)
-   [`WebGL2RenderingContext.compressedTexImage3D()`](../webglrenderingcontext/compressedteximage2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/compressedTexSubImage3D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/compressedTexSubImage3D</a>
