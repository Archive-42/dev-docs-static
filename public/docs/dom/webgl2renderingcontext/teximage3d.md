WebGL2RenderingContext.texImage3D()
===================================

The `WebGLRenderingContext.texImage3D()` method of the [WebGL API](../webgl_api) specifies a three-dimensional texture image.

Syntax
------

    void gl.texImage3D(target, level, internalformat, width, height, depth, border, format, type, GLintptr offset);

    void gl.texImage3D(target, level, internalformat, width, height, depth, border, format, type, HTMLCanvasElement source);
    void gl.texImage3D(target, level, internalformat, width, height, depth, border, format, type, HTMLImageElement source);
    void gl.texImage3D(target, level, internalformat, width, height, depth, border, format, type, HTMLVideoElement source);
    void gl.texImage3D(target, level, internalformat, width, height, depth, border, format, type, ImageBitmap source);
    void gl.texImage3D(target, level, internalformat, width, height, depth, border, format, type, ImageData source);
    void gl.texImage3D(target, level, internalformat, width, height, depth, border, format, type, ArrayBufferView? srcData);
    void gl.texImage3D(target, level, internalformat, width, height, depth, border, format, type, ArrayBufferView srcData, srcOffset);

### Parameters

`target`  
A [`GLenum`](../webgl_api/types) specifying the binding point (target) of the active texture. Possible values:

-   `gl.TEXTURE_3D`: A three-dimensional texture.
-   `gl.TEXTURE_2D_ARRAY`: A two-dimensional array texture.

`level`  
A [`GLint`](../webgl_api/types) specifying the level of detail. Level 0 is the base image level and level *n* is the *n*th mipmap reduction level.

`internalformat`  
A [`GLint`](../webgl_api/types) specifying the color components in the texture. Possible values:

-   `gl.ALPHA`: Discards the red, green and blue components and reads the alpha component.
-   `gl.RGB`: Discards the alpha components and reads the red, green and blue components.
-   `gl.RGBA`: Red, green, blue and alpha components are read from the color buffer.
-   `gl.LUMINANCE`: Each color component is a luminance component, alpha is 1.0.
-   `gl.LUMINANCE_ALPHA`: Each component is a luminance/alpha component.
-   `gl.R8`
-   `gl.R16F`
-   `gl.`R32F
-   `gl.R8UI`
-   `gl.RG8`
-   `gl.RG16F`
-   `gl.RG32F`
-   `gl.RGUI`
-   `gl.RGB8`
-   `gl.SRGB8`
-   `gl.RGB565`
-   `gl.R11F_G11F_B10F`
-   `gl.RGB9_E5`
-   `gl.RGB16F`
-   `gl.RGB32F`
-   `gl.RGB8UI`
-   `gl.RGBA8`
-   `gl.SRGB_APLHA8`
-   `gl.RGB5_A1`
-   `gl.RGBA4444`
-   `gl.RGBA16F`
-   `gl.RGBA32F`
-   `gl.RGBA8UI`

`width`  
A [`GLsizei`](../webgl_api/types) specifying the width of the texture.

`height`  
A [`GLsizei`](../webgl_api/types) specifying the height of the texture.

`depth`  
A [`GLsizei`](../webgl_api/types) specifying the depth of the texture.

`border`  
A [`GLint`](../webgl_api/types) specifying the width of the border. Must be 0.

`format`  
A [`GLenum`](../webgl_api/types) specifying the format of the texel data. The correct combinations with `internalformat` are listed in [this table](https://www.khronos.org/registry/webgl/specs/latest/2.0/#TEXTURE_TYPES_FORMATS_FROM_DOM_ELEMENTS_TABLE).

`type`  
A [`GLenum`](../webgl_api/types) specifying the data type of the texel data. Possible values:

-   `gl.UNSIGNED_BYTE`: 8 bits per channel for `gl.RGBA`
-   `gl.UNSIGNED_SHORT_5_6_5`: 5 red bits, 6 green bits, 5 blue bits.
-   `gl.UNSIGNED_SHORT_4_4_4_4`: 4 red bits, 4 green bits, 4 blue bits, 4 alpha bits.
-   `gl.UNSIGNED_SHORT_5_5_5_1`: 5 red bits, 5 green bits, 5 blue bits, 1 alpha bit.
-   `gl.BYTE`
-   `gl.UNSIGNED_SHORT`
-   `gl.SHORT`
-   `gl.UNSIGNED_INT`
-   `gl.INT`
-   `gl.HALF_FLOAT`
-   `gl.FLOAT`
-   `gl.UNSIGNED_INT_2_10_10_10_REV`
-   `gl.UNSIGNED_INT_10F_11F_11F_REV`
-   `gl.UNSIGNED_INT_5_9_9_9_REV`
-   `gl.UNSIGNED_INT_24_8`
-   `gl.FLOAT_32_UNSIGNED_INT_24_8_REV` (pixels must be [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null))

`source`  
One of the following objects can be used as a pixel source for the texture:

-   [`ArrayBufferView`](../arraybufferview),
-   [`ImageBitmap`](../imagebitmap),
-   [`ImageData`](../imagedata),
-   [`HTMLImageElement`](../htmlimageelement),
-   [`HTMLCanvasElement`](../htmlcanvaselement),
-   [`HTMLVideoElement`](../htmlvideoelement).

offset  
A [`GLintptr`](../webgl_api/types) byte offset into the [`WebGLBuffer`](../webglbuffer)'s data store. Used to upload data to the currently bound [`WebGLTexture`](../webgltexture) from the `WebGLBuffer` bound to the `PIXEL_UNPACK_BUFFER` target.

### Return value

None.

Examples
--------

    gl.texImage3D(gl.TEXTURE_3D,
                  0,                                          // level
                  gl.RGBA,                                    // internalFormat
                  1,                                          // width
                  1,                                          // height
                  1,                                          // depth
                  0,                                          // border
                  gl.RGBA,                                    // format
                  gl.UNSIGNED_BYTE,                           // type
                  new Uint8Array([0xff, 0x00, 0x00, 0x00]));  // data

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.6">WebGL 2.0<br />
<span class="small">The definition of 'texImage3D' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glTexImage3D.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glTexImage3D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`texImage3D`

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

See also
--------

-   [`WebGLRenderingContext.createTexture()`](../webglrenderingcontext/createtexture)
-   [`WebGLRenderingContext.bindTexture()`](../webglrenderingcontext/bindtexture)
-   [`WebGLRenderingContext.texSubImage2D()`](../webglrenderingcontext/texsubimage2d)
-   [`WebGLRenderingContext.compressedTexImage2D()`](../webglrenderingcontext/compressedteximage2d)
-   [`WebGLRenderingContext.copyTexImage2D()`](../webglrenderingcontext/copyteximage2d)
-   [`WebGLRenderingContext.getTexParameter()`](../webglrenderingcontext/gettexparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/texImage3D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/texImage3D</a>
