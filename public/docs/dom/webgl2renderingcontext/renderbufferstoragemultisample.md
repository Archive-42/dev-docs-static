WebGL2RenderingContext.renderbufferStorageMultisample()
=======================================================

The `WebGL2RenderingContext.renderbufferStorageMultisample()` method of the [WebGL 2 API](../webgl_api) returns creates and initializes a renderbuffer object's data store and allows specifying a number of samples to be used.

Syntax
------

    void gl.renderbufferStorageMultisample(target, samples, internalFormat, width, height);

### Parameters

target  
A [`GLenum`](../webgl_api/types) specifying the target renderbuffer object. Possible values:

-   `gl.RENDERBUFFER`: Buffer data storage for single images in a renderable internal format.

samples  
A [`GLsizei`](../webgl_api/types) specifying the number of samples to be used for the renderbuffer storage.

internalFormat  
A [`GLenum`](../webgl_api/types) specifying the internal format of the renderbuffer. Possible values (\`gl.DEPTH\_STENCIL\` is not supported):

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
-   `gl.SRGB8_ALPHA8`
-   `gl.RGBA4`
-   `gl.RGB565`
-   `gl.RGB5_A1`
-   `gl.RGB10_A2`
-   `gl.RGBA8UI`
-   `gl.RGBA8I`
-   `gl.RGB10_A2UI`
-   `gl.RGBA16UI`
-   `gl.RGBA16I`
-   `gl.RGBA32I`
-   `gl.RGBA32UI`
-   `gl.DEPTH_COMPONENT16`
-   `gl.DEPTH_COMPONENT24`
-   `gl.DEPTH_COMPONENT32F`
-   `gl.DEPTH_STENCIL`
-   `gl.DEPTH24_STENCIL8`
-   `gl.DEPTH32F_STENCIL8`
-   `gl.STENCIL_INDEX8`

width  
A [`GLsizei`](../webgl_api/types) specifying the width of the renderbuffer in pixels.

height  
A [`GLsizei`](../webgl_api/types) specifying the height of the renderbuffer in pixels.

### Return value

None.

Examples
--------

    gl.renderbufferStorageMultisample(gl.RENDERBUFFER, 4, gl.RBGA4, 256, 256);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.5">WebGL 2.0<br />
<span class="small">The definition of 'glRenderbufferStorageMultisample' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glRenderbufferStorageMultisample.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glRenderbufferStorageMultisample' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3 API.</td></tr></tbody></table>

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

`renderbufferStorageMultisample`

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

-   [`WebGLRenderingContext.renderbufferStorage()`](../webglrenderingcontext/renderbufferstorage)
-   [`WebGLRenderingContext.bindRenderbuffer()`](../webglrenderingcontext/bindrenderbuffer)
-   [`WebGLRenderingContext.createRenderbuffer()`](../webglrenderingcontext/createrenderbuffer)
-   [`WebGLRenderingContext.deleteRenderbuffer()`](../webglrenderingcontext/deleterenderbuffer)
-   [`WebGLRenderingContext.getRenderbufferParameter()`](../webglrenderingcontext/getrenderbufferparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/renderbufferStorageMultisample" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/renderbufferStorageMultisample</a>
