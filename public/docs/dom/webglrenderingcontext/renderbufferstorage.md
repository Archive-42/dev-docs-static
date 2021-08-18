WebGLRenderingContext.renderbufferStorage()
===========================================

The `WebGLRenderingContext.renderbufferStorage()` method of the [WebGL API](../webgl_api) creates and initializes a renderbuffer object's data store.

Syntax
------

    void gl.renderbufferStorage(target, internalFormat, width, height);

### Parameters

target  
A [`Glenum`](../webgl_api/types) specifying the target renderbuffer object. Possible values:

-   `gl.RENDERBUFFER`: Buffer data storage for single images in a renderable internal format.

internalFormat  
A [`Glenum`](../webgl_api/types) specifying the internal format of the renderbuffer. Possible values:

-   `gl.RGBA4`: 4 red bits, 4 green bits, 4 blue bits 4 alpha bits.
-   `gl.RGB565`: 5 red bits, 6 green bits, 5 blue bits.
-   `gl.RGB5_A1`: 5 red bits, 5 green bits, 5 blue bits, 1 alpha bit.
-   `gl.DEPTH_COMPONENT16`: 16 depth bits.
-   `gl.STENCIL_INDEX8`: 8 stencil bits.
-   `gl.DEPTH_STENCIL`
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.R8`
    -   `gl.R8UI`
    -   `gl.R8I`
    -   `gl.R16UI`
    -   `gl.R16I`
    -   `gl.R32UI`
    -   `gl.R32I`
    -   `gl.RG8`
    -   `gl.RG8UI`
    -   `gl.RG8I`
    -   `gl.RG16UI`
    -   `gl.RG16I`
    -   `gl.RG32UI`
    -   `gl.RG32I`
    -   `gl.RGB8`
    -   `gl.RGBA8`
    -   `gl.SRGB8_ALPHA8` (also available as an extension for WebGL 1, see below)
    -   `gl.RGB10_A2`
    -   `gl.RGBA8UI`
    -   `gl.RGBA8I`
    -   `gl.RGB10_A2UI`
    -   `gl.RGBA16UI`
    -   `gl.RGBA16I`
    -   `gl.RGBA32I`
    -   `gl.RGBA32UI`
    -   `gl.DEPTH_COMPONENT24`
    -   `gl.DEPTH_COMPONENT32F`
    -   `gl.DEPTH24_STENCIL8`
    -   `gl.DEPTH32F_STENCIL8`
-   When using the [`WEBGL_color_buffer_float`](../webgl_color_buffer_float) extension:
    -   `ext.RGBA32F_EXT`: RGBA 32-bit floating-point type.
    -   `ext.RGB32F_EXT`: RGB 32-bit floating-point type.
-   When using the [`EXT_sRGB`](../ext_srgb) extension:
    -   `ext.SRGB8_ALPHA8_EXT`: 8-bit sRGB and alpha.
-   When using a [WebGL 2 context](../webgl2renderingcontext) and the [`EXT_color_buffer_float`](../ext_color_buffer_float) extension:
    -   `gl.R16F`
    -   `gl.RG16F`
    -   `gl.RGBA16F`
    -   `gl.R32F`
    -   `gl.RG32F`
    -   `gl.RGBA32F`
    -   `gl.R11F_G11F_B10F`

width  
A [`GLsizei`](../webgl_api/types) specifying the width of the renderbuffer in pixels.

height  
A [`GLsizei`](../webgl_api/types) specifying the height of the renderbuffer in pixels.

### Return value

None.

Examples
--------

    gl.renderbufferStorage(gl.RENDERBUFFER, gl.RGBA4, 256, 256);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.7">WebGL 1.0<br />
<span class="small">The definition of 'renderbufferStorage' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glRenderbufferStorage.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glRenderbufferStorage' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL ES 2 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.5">WebGL 2.0<br />
<span class="small">The definition of 'getRenderbufferParameter' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL 2.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glRenderbufferStorage.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glRenderbufferStorage' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3 API.<br />
Adds many new internal formats.</td></tr></tbody></table>

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

`renderbufferStorage`

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

-   [`WebGLRenderingContext.bindRenderbuffer()`](bindrenderbuffer)
-   [`WebGLRenderingContext.createRenderbuffer()`](createrenderbuffer)
-   [`WebGLRenderingContext.deleteRenderbuffer()`](deleterenderbuffer)
-   [`WebGLRenderingContext.getRenderbufferParameter()`](getrenderbufferparameter)
-   [`WEBGL_color_buffer_float`](../webgl_color_buffer_float)
-   [`EXT_sRGB`](../ext_srgb)
-   [`EXT_color_buffer_float`](../ext_color_buffer_float)
-   [`EXT_texture_norm16`](../ext_texture_norm16)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/renderbufferStorage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/renderbufferStorage</a>
