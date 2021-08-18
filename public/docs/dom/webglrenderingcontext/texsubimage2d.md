WebGLRenderingContext.texSubImage2D()
=====================================

The `WebGLRenderingContext.texSubImage2D()` method of the [WebGL API](../webgl_api) specifies a sub-rectangle of the current texture.

Syntax
------

    // WebGL 1:
    void gl.texSubImage2D(target, level, xoffset, yoffset, width, height, format, type, ArrayBufferView? pixels);
    void gl.texSubImage2D(target, level, xoffset, yoffset, format, type, ImageData? pixels);
    void gl.texSubImage2D(target, level, xoffset, yoffset, format, type, HTMLImageElement? pixels);
    void gl.texSubImage2D(target, level, xoffset, yoffset, format, type, HTMLCanvasElement? pixels);
    void gl.texSubImage2D(target, level, xoffset, yoffset, format, type, HTMLVideoElement? pixels);
    void gl.texSubImage2D(target, level, xoffset, yoffset, format, type, ImageBitmap? pixels);

    // WebGL 2:
    void gl.texSubImage2D(target, level, xoffset, yoffset, width, height, format, type, GLintptr offset);
    void gl.texSubImage2D(target, level, xoffset, yoffset, width, height, format, type, HTMLCanvasElement source);
    void gl.texSubImage2D(target, level, xoffset, yoffset, width, height, format, type, HTMLImageElement source);
    void gl.texSubImage2D(target, level, xoffset, yoffset, width, height, format, type, HTMLVideoElement source);
    void gl.texSubImage2D(target, level, xoffset, yoffset, width, height, format, type, ImageBitmap source);
    void gl.texSubImage2D(target, level, xoffset, yoffset, width, height, format, type, ImageData source);
    void gl.texSubImage2D(target, level, xoffset, yoffset, width, height, format, type, ArrayBufferView srcData, srcOffset);

### Parameters

`target`  
A [`GLenum`](../webgl_api/types) specifying the binding point (target) of the active texture. Possible values:

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
A [`GLint`](../webgl_api/types) specifying the lower left texel x coordinate of a width-wide by height-wide rectangular subregion of the texture array.

`yoffset`  
A [`GLint`](../webgl_api/types) specifying the lower left texel y coordinate of a width-wide by height-wide rectangular subregion of the texture array..

`width`  
A [`GLsizei`](../webgl_api/types) specifying the width of the texture in texels.

`height`  
A [`GLsizei`](../webgl_api/types) specifying the height of the texture in texels.

`format`  
A [`GLenum`](../webgl_api/types) specifying the format of the texel data. Possible values:

-   `gl.ALPHA`: Discards the red, green and blue components and reads the alpha component.
-   `gl.RGB`: Discards the alpha components and reads the red, green and blue components.
-   `gl.RGBA`: Red, green, blue and alpha components are read from the color buffer.
-   `gl.LUMINANCE`: Each color component is a luminance component, alpha is 1.0.
-   `gl.LUMINANCE_ALPHA`: Each component is a luminance/alpha component.
-   When using the [`EXT_sRGB`](../ext_srgb) extension:
    -   `ext.SRGB_EXT`
    -   `ext.SRGB_ALPHA_EXT`
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.RED`
    -   `gl.RG`
    -   `gl.RED_INTEGER`
    -   `gl.RG_INTEGER`
    -   `gl.RGB_INTEGER`
    -   `gl.RGBA_INTEGER`

`type`  
A [`GLenum`](../webgl_api/types) specifying the data type of the texel data. Possible values:

-   `gl.UNSIGNED_BYTE`: 8 bits per channel for `gl.RGBA`
-   `gl.UNSIGNED_SHORT_5_6_5`: 5 red bits, 6 green bits, 5 blue bits.
-   `gl.UNSIGNED_SHORT_4_4_4_4`: 4 red bits, 4 green bits, 4 blue bits, 4 alpha bits.
-   `gl.UNSIGNED_SHORT_5_5_5_1`: 5 red bits, 5 green bits, 5 blue bits, 1 alpha bit.
-   When using the [`OES_texture_float`](../oes_texture_float) extension:
    -   `gl.FLOAT`
-   When using the [`OES_texture_half_float`](../oes_texture_half_float) extension:
    -   `gl.HALF_FLOAT_OES`
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
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

`pixels`  
One of the following objects can be used as a pixel source for the texture:

-   [`ArrayBufferView`](../arraybufferview),
    -   A [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) must be used if `type` is `gl.UNSIGNED_BYTE`.
    -   A [`Uint16Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint16Array) must be used if `type` is either `gl.UNSIGNED_SHORT_5_6_5`, `gl.UNSIGNED_SHORT_4_4_4_4`, `gl.UNSIGNED_SHORT_5_5_5_1`, or `ext.HALF_FLOAT_OES`.
    -   A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) must be used if `type` is `gl.FLOAT`.
-   [`ImageData`](../imagedata),
-   [`HTMLImageElement`](../htmlimageelement),
-   [`HTMLCanvasElement`](../htmlcanvaselement),
-   [`HTMLVideoElement`](../htmlvideoelement),
-   [`ImageBitmap`](../imagebitmap).

offset  
(WebGL 2 only) A [`GLintptr`](../webgl_api/types) byte offset into the [`WebGLBuffer`](../webglbuffer)'s data store. Used to upload data to the currently bound [`WebGLTexture`](../webgltexture) from the `WebGLBuffer` bound to the `PIXEL_UNPACK_BUFFER` target.

### Return value

None.

Examples
--------

    gl.texSubImage2D(gl.TEXTURE_2D, 0, 0, 0, gl.RGBA, gl.UNSIGNED_BYTE, image);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#TEXSUBIMAGE2D">WebGL 1.0<br />
<span class="small">The definition of 'texSubImage2D' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glTexSubImage2D.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glTexSubImage2D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2.0 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.6">WebGL 2.0<br />
<span class="small">The definition of 'texSubImage2D' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glTexSubImage2D.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glTexSubImage2D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`texSubImage2D`

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

-   [`WebGLRenderingContext.createTexture()`](createtexture)
-   [`WebGLRenderingContext.bindTexture()`](bindtexture)
-   [`WebGLRenderingContext.texImage2D()`](teximage2d)
-   [`WebGLRenderingContext.compressedTexImage2D()`](compressedteximage2d)
-   [`WebGLRenderingContext.copyTexImage2D()`](copyteximage2d)
-   [`WebGLRenderingContext.getTexParameter()`](gettexparameter)
-   [`OES_texture_float`](../oes_texture_float)
-   [`OES_texture_half_float`](../oes_texture_half_float)
-   [`EXT_sRGB`](../ext_srgb)
-   [`EXT_texture_norm16`](../ext_texture_norm16)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/texSubImage2D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/texSubImage2D</a>
