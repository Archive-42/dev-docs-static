WebGLRenderingContext.texImage2D()
==================================

The `WebGLRenderingContext.texImage2D()` method of the [WebGL API](../webgl_api) specifies a two-dimensional texture image.

Syntax
------

    // WebGL1:
    void gl.texImage2D(target, level, internalformat, width, height, border, format, type, ArrayBufferView? pixels);
    void gl.texImage2D(target, level, internalformat, format, type, ImageData? pixels);
    void gl.texImage2D(target, level, internalformat, format, type, HTMLImageElement? pixels);
    void gl.texImage2D(target, level, internalformat, format, type, HTMLCanvasElement? pixels);
    void gl.texImage2D(target, level, internalformat, format, type, HTMLVideoElement? pixels);
    void gl.texImage2D(target, level, internalformat, format, type, ImageBitmap? pixels);

    // WebGL2:
    void gl.texImage2D(target, level, internalformat, width, height, border, format, type, GLintptr offset);
    void gl.texImage2D(target, level, internalformat, width, height, border, format, type, HTMLCanvasElement source);
    void gl.texImage2D(target, level, internalformat, width, height, border, format, type, HTMLImageElement source);
    void gl.texImage2D(target, level, internalformat, width, height, border, format, type, HTMLVideoElement source);
    void gl.texImage2D(target, level, internalformat, width, height, border, format, type, ImageBitmap source);
    void gl.texImage2D(target, level, internalformat, width, height, border, format, type, ImageData source);
    void gl.texImage2D(target, level, internalformat, width, height, border, format, type, ArrayBufferView srcData, srcOffset);

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

`internalformat`

A [`GLenum`](../webgl_api/types) specifying the color components in the texture.

Possible values in both WebGL1 and WebGL2

<table><thead><tr class="header"><th>Format</th><th>Type</th><th>Channels</th><th>Bytes per pixel</th></tr></thead><tbody><tr class="odd"><td>RGBA</td><td>UNSIGNED_BYTE</td><td>4</td><td>4</td></tr><tr class="even"><td>RGB</td><td>UNSIGNED_BYTE</td><td>3</td><td>3</td></tr><tr class="odd"><td>RGBA</td><td>UNSIGNED_SHORT_4_4_4_4</td><td>4</td><td>2</td></tr><tr class="even"><td>RGBA</td><td>UNSIGNED_SHORT_5_5_5_1</td><td>4</td><td>2</td></tr><tr class="odd"><td>RGB</td><td>UNSIGNED_SHORT_5_6_5</td><td>3</td><td>2</td></tr><tr class="even"><td>LUMINANCE_ALPHA</td><td>UNSIGNED_BYTE</td><td>2</td><td>2</td></tr><tr class="odd"><td>LUMINANCE</td><td>UNSIGNED_BYTE</td><td>1</td><td>1</td></tr><tr class="even"><td>ALPHA</td><td>UNSIGNED_BYTE</td><td>1</td><td>1</td></tr></tbody></table>

Other possible values in WebGL2 for the versions of `texImage2D` that take an `ArrayBufferView` or a `GLintptr offset`

<table><thead><tr class="header"><th><strong>Sized<br />
Format</strong></th><th><strong>Base<br />
Format</strong></th><th><strong>R<br />
bits</strong></th><th><strong>G<br />
bits</strong></th><th><strong>B<br />
bits</strong></th><th><strong>A<br />
bits</strong></th><th><strong>Shared<br />
bits</strong></th><th><strong>Color<br />
renderable</strong></th><th><strong>Texture<br />
filterable</strong></th></tr></thead><tbody><tr class="odd"><td>R8</td><td>RED</td><td>8</td><td></td><td></td><td></td><td></td><td>●</td><td>●</td></tr><tr class="even"><td>R8_SNORM</td><td>RED</td><td>s8</td><td></td><td></td><td></td><td></td><td></td><td>●</td></tr><tr class="odd"><td>RG8</td><td>RG</td><td>8</td><td>8</td><td></td><td></td><td></td><td>●</td><td>●</td></tr><tr class="even"><td>RG8_SNORM</td><td>RG</td><td>s8</td><td>s8</td><td></td><td></td><td></td><td></td><td>●</td></tr><tr class="odd"><td>RGB8</td><td>RGB</td><td>8</td><td>8</td><td>8</td><td></td><td></td><td>●</td><td>●</td></tr><tr class="even"><td>RGB8_SNORM</td><td>RGB</td><td>s8</td><td>s8</td><td>s8</td><td></td><td></td><td></td><td>●</td></tr><tr class="odd"><td>RGB565</td><td>RGB</td><td>5</td><td>6</td><td>5</td><td></td><td></td><td>●</td><td>●</td></tr><tr class="even"><td>RGBA4</td><td>RGBA</td><td>4</td><td>4</td><td>4</td><td>4</td><td></td><td>●</td><td>●</td></tr><tr class="odd"><td>RGB5_A1</td><td>RGBA</td><td>5</td><td>5</td><td>5</td><td>1</td><td></td><td>●</td><td>●</td></tr><tr class="even"><td>RGBA8</td><td>RGBA</td><td>8</td><td>8</td><td>8</td><td>8</td><td></td><td>●</td><td>●</td></tr><tr class="odd"><td>RGBA8_SNORM</td><td>RGBA</td><td>s8</td><td>s8</td><td>s8</td><td>s8</td><td></td><td></td><td>●</td></tr><tr class="even"><td>RGB10_A2</td><td>RGBA</td><td>10</td><td>10</td><td>10</td><td>2</td><td></td><td>●</td><td>●</td></tr><tr class="odd"><td>RGB10_A2UI</td><td>RGBA</td><td>ui10</td><td>ui10</td><td>ui10</td><td>ui2</td><td></td><td>●</td><td></td></tr><tr class="even"><td>SRGB8</td><td>RGB</td><td>8</td><td>8</td><td>8</td><td></td><td></td><td></td><td>●</td></tr><tr class="odd"><td>SRGB8_ALPHA8</td><td>RGBA</td><td>8</td><td>8</td><td>8</td><td>8</td><td></td><td>●</td><td>●</td></tr><tr class="even"><td>R16F</td><td>RED</td><td>f16</td><td></td><td></td><td></td><td></td><td></td><td>●</td></tr><tr class="odd"><td>RG16F</td><td>RG</td><td>f16</td><td>f16</td><td></td><td></td><td></td><td></td><td>●</td></tr><tr class="even"><td>RGB16F</td><td>RGB</td><td>f16</td><td>f16</td><td>f16</td><td></td><td></td><td></td><td>●</td></tr><tr class="odd"><td>RGBA16F</td><td>RGBA</td><td>f16</td><td>f16</td><td>f16</td><td>f16</td><td></td><td></td><td>●</td></tr><tr class="even"><td>R32F</td><td>RED</td><td>f32</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr class="odd"><td>RG32F</td><td>RG</td><td>f32</td><td>f32</td><td></td><td></td><td></td><td></td><td></td></tr><tr class="even"><td>RGB32F</td><td>RGB</td><td>f32</td><td>f32</td><td>f32</td><td></td><td></td><td></td><td></td></tr><tr class="odd"><td>RGBA32F</td><td>RGBA</td><td>f32</td><td>f32</td><td>f32</td><td>f32</td><td></td><td></td><td></td></tr><tr class="even"><td>R11F_G11F_B10F</td><td>RGB</td><td>f11</td><td>f11</td><td>f10</td><td></td><td></td><td></td><td>●</td></tr><tr class="odd"><td>RGB9_E5</td><td>RGB</td><td>9</td><td>9</td><td>9</td><td></td><td>5</td><td></td><td>●</td></tr><tr class="even"><td>R8I</td><td>RED</td><td>i8</td><td></td><td></td><td></td><td></td><td>●</td><td></td></tr><tr class="odd"><td>R8UI</td><td>RED</td><td>ui8</td><td></td><td></td><td></td><td></td><td>●</td><td></td></tr><tr class="even"><td>R16I</td><td>RED</td><td>i16</td><td></td><td></td><td></td><td></td><td>●</td><td></td></tr><tr class="odd"><td>R16UI</td><td>RED</td><td>ui16</td><td></td><td></td><td></td><td></td><td>●</td><td></td></tr><tr class="even"><td>R32I</td><td>RED</td><td>i32</td><td></td><td></td><td></td><td></td><td>●</td><td></td></tr><tr class="odd"><td>R32UI</td><td>RED</td><td>ui32</td><td></td><td></td><td></td><td></td><td>●</td><td></td></tr><tr class="even"><td>RG8I</td><td>RG</td><td>i8</td><td>i8</td><td></td><td></td><td></td><td>●</td><td></td></tr><tr class="odd"><td>RG8UI</td><td>RG</td><td>ui8</td><td>ui8</td><td></td><td></td><td></td><td>●</td><td></td></tr><tr class="even"><td>RG16I</td><td>RG</td><td>i16</td><td>i16</td><td></td><td></td><td></td><td>●</td><td></td></tr><tr class="odd"><td>RG16UI</td><td>RG</td><td>ui16</td><td>ui16</td><td></td><td></td><td></td><td>●</td><td></td></tr><tr class="even"><td>RG32I</td><td>RG</td><td>i32</td><td>i32</td><td></td><td></td><td></td><td>●</td><td></td></tr><tr class="odd"><td>RG32UI</td><td>RG</td><td>ui32</td><td>ui32</td><td></td><td></td><td></td><td>●</td><td></td></tr><tr class="even"><td>RGB8I</td><td>RGB</td><td>i8</td><td>i8</td><td>i8</td><td></td><td></td><td></td><td></td></tr><tr class="odd"><td>RGB8UI</td><td>RGB</td><td>ui8</td><td>ui8</td><td>ui8</td><td></td><td></td><td></td><td></td></tr><tr class="even"><td>RGB16I</td><td>RGB</td><td>i16</td><td>i16</td><td>i16</td><td></td><td></td><td></td><td></td></tr><tr class="odd"><td>RGB16UI</td><td>RGB</td><td>ui16</td><td>ui16</td><td>ui16</td><td></td><td></td><td></td><td></td></tr><tr class="even"><td>RGB32I</td><td>RGB</td><td>i32</td><td>i32</td><td>i32</td><td></td><td></td><td></td><td></td></tr><tr class="odd"><td>RGB32UI</td><td>RGB</td><td>ui32</td><td>ui32</td><td>ui32</td><td></td><td></td><td></td><td></td></tr><tr class="even"><td>RGBA8I</td><td>RGBA</td><td>i8</td><td>i8</td><td>i8</td><td>i8</td><td></td><td>●</td><td></td></tr><tr class="odd"><td>RGBA8UI</td><td>RGBA</td><td>ui8</td><td>ui8</td><td>ui8</td><td>ui8</td><td></td><td>●</td><td></td></tr><tr class="even"><td>RGBA16I</td><td>RGBA</td><td>i16</td><td>i16</td><td>i16</td><td>i16</td><td></td><td>●</td><td></td></tr><tr class="odd"><td>RGBA16UI</td><td>RGBA</td><td>ui16</td><td>ui16</td><td>ui16</td><td>ui16</td><td></td><td>●</td><td></td></tr><tr class="even"><td>RGBA32I</td><td>RGBA</td><td>i32</td><td>i32</td><td>i32</td><td>i32</td><td></td><td>●</td><td></td></tr><tr class="odd"><td>RGBA32UI</td><td>RGBA</td><td>ui32</td><td>ui32</td><td>ui32</td><td>ui32</td><td></td><td>●</td><td></td></tr></tbody></table>

Possible values in WebGL2 for the versions of `texImage2D` that take a texture an `HTMLImageElement`, `HTMLCanvasElement`, `HTMLVideoElement`, `ImageBitmap`, or `ImageData`

-   `gl.ALPHA`: Discards the red, green and blue components and reads the alpha component.
-   `gl.RGB`: Discards the alpha components and reads the red, green and blue components.
-   `gl.RGBA`: Red, green, blue and alpha components are read from the color buffer.
-   `gl.LUMINANCE`: Each color component is a luminance component, alpha is 1.0.
-   `gl.LUMINANCE_ALPHA`: Each component is a luminance/alpha component.
-   When using the [`WEBGL_depth_texture`](../webgl_depth_texture) extension:
    -   `gl.DEPTH_COMPONENT`
    -   `gl.DEPTH_STENCIL`
-   When using the [`EXT_sRGB`](../ext_srgb) extension:
    -   `ext.SRGB_EXT`
    -   `ext.SRGB_ALPHA_EXT`
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.R8`
    -   `gl.R16F`
    -   `gl.R32F`
    -   `gl.R8UI`
    -   `gl.RG8`
    -   `gl.RG16F`
    -   `gl.RG32F`
    -   `gl.RG8UI`
    -   `gl.RG16UI`
    -   `gl.RG32UI`
    -   `gl.RGB8`
    -   `gl.SRGB8`
    -   `gl.RGB565`
    -   `gl.R11F_G11F_B10F`
    -   `gl.RGB9_E5`
    -   `gl.RGB16F`
    -   `gl.RGB32F`
    -   `gl.RGB8UI`
    -   `gl.RGBA8`
    -   `gl.SRGB8_ALPHA8`
    -   `gl.RGB5_A1`
    -   `gl.RGB10_A2`
    -   `gl.RGBA4`
    -   `gl.RGBA16F`
    -   `gl.RGBA32F`
    -   `gl.RGBA8UI`

`width`  
A [`GLsizei`](../webgl_api/types) specifying the width of the texture.

`height`  
A [`GLsizei`](../webgl_api/types) specifying the height of the texture.

`border`  
A [`GLint`](../webgl_api/types) specifying the width of the border. Must be 0.

`format`  
A [`GLenum`](../webgl_api/types) specifying the format of the texel data. In WebGL 1, this must be the same as `internalformat` (see above). in WebGL 2, the combinations are listed in [this table](https://www.khronos.org/registry/webgl/specs/latest/2.0/#TEXTURE_TYPES_FORMATS_FROM_DOM_ELEMENTS_TABLE).

`type`  
A [`GLenum`](../webgl_api/types) specifying the data type of the texel data. Possible values:

-   `gl.UNSIGNED_BYTE`: 8 bits per channel for `gl.RGBA`
-   `gl.UNSIGNED_SHORT_5_6_5`: 5 red bits, 6 green bits, 5 blue bits.
-   `gl.UNSIGNED_SHORT_4_4_4_4`: 4 red bits, 4 green bits, 4 blue bits, 4 alpha bits.
-   `gl.UNSIGNED_SHORT_5_5_5_1`: 5 red bits, 5 green bits, 5 blue bits, 1 alpha bit.
-   When using the [`WEBGL_depth_texture`](../webgl_depth_texture) extension:
    -   `gl.UNSIGNED_SHORT`
    -   `gl.UNSIGNED_INT`
    -   `ext.UNSIGNED_INT_24_8_WEBGL` (constant provided by the extension)
-   When using the [`OES_texture_float`](../oes_texture_float) extension:
    -   `gl.FLOAT`
-   When using the [`OES_texture_half_float`](../oes_texture_half_float) extension:
    -   `ext.HALF_FLOAT_OES` (constant provided by the extension)
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
    -   A [`Uint16Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint16Array) must be used if `type` is either `gl.UNSIGNED_SHORT_5_6_5`, `gl.UNSIGNED_SHORT_4_4_4_4`, `gl.UNSIGNED_SHORT_5_5_5_1`, `gl.UNSIGNED_SHORT` or `ext.HALF_FLOAT_OES`.
    -   A [`Uint32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array) must be used if `type` is `gl.UNSIGNED_INT` or `ext.UNSIGNED_INT_24_8_WEBGL`.
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

    gl.texImage2D(gl.TEXTURE_2D, 0, gl.RGBA, gl.RGBA, gl.UNSIGNED_BYTE, image);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.8">WebGL 1.0<br />
<span class="small">The definition of 'texImage2D' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glTexImage2D.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glTexImage2D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2.0 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.6">WebGL 2.0<br />
<span class="small">The definition of 'texImage2D' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glTexImage2D.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glTexImage2D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`texImage2D`

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
-   [`WebGLRenderingContext.texSubImage2D()`](texsubimage2d)
-   [`WebGLRenderingContext.compressedTexImage2D()`](compressedteximage2d)
-   [`WebGLRenderingContext.copyTexImage2D()`](copyteximage2d)
-   [`WebGLRenderingContext.getTexParameter()`](gettexparameter)
-   [`WEBGL_depth_texture`](../webgl_depth_texture)
-   [`OES_texture_float`](../oes_texture_float)
-   [`OES_texture_half_float`](../oes_texture_half_float)
-   [`EXT_texture_norm16`](../ext_texture_norm16)
-   [`EXT_sRGB`](../ext_srgb)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/texImage2D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/texImage2D</a>
