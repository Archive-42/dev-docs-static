WebGLRenderingContext.getRenderbufferParameter()
================================================

The `WebGLRenderingContext.getRenderbufferParameter()` method of the [WebGL API](../webgl_api) returns information about the renderbuffer.

Syntax
------

    any gl.getRenderbufferParameter(target, pname);

### Parameters

target  
A [`Glenum`](../webgl_api/types) specifying the target renderbuffer object. Possible values:

-   `gl.RENDERBUFFER`: Buffer data storage for single images in a renderable internal format.

pname  
A [`Glenum`](../webgl_api/types) specifying the information to query. Possible values:

-   `gl.RENDERBUFFER_WIDTH`: Returns a [`GLint`](../webgl_api/types) indicating the width of the image of the currently bound renderbuffer.
-   `gl.RENDERBUFFER_HEIGHT`: Returns a [`GLint`](../webgl_api/types) indicating the height of the image of the currently bound renderbuffer.
-   `gl.RENDERBUFFER_INTERNAL_FORMAT`: Returns a [`GLenum`](../webgl_api/types) indicating the internal format of the currently bound renderbuffer. The default is `gl.RGBA4`. Possible return values:
    -   `gl.RGBA4`: 4 red bits, 4 green bits, 4 blue bits 4 alpha bits.
    -   `gl.RGB565`: 5 red bits, 6 green bits, 5 blue bits.
    -   `gl.RGB5_A1`: 5 red bits, 5 green bits, 5 blue bits, 1 alpha bit.
    -   `gl.DEPTH_COMPONENT16`: 16 depth bits.
    -   `gl.STENCIL_INDEX8`: 8 stencil bits.
-   `gl.RENDERBUFFER_GREEN_SIZE`: Returns a [`GLint`](../webgl_api/types) that is the resolution size (in bits) for the green color.
-   `gl.RENDERBUFFER_BLUE_SIZE`: Returns a [`GLint`](../webgl_api/types) that is the resolution size (in bits) for the blue color.
-   `gl.RENDERBUFFER_RED_SIZE`: Returns a [`GLint`](../webgl_api/types) that is the resolution size (in bits) for the red color.
-   `gl.RENDERBUFFER_ALPHA_SIZE`: Returns a [`GLint`](../webgl_api/types) that is the resolution size (in bits) for the alpha component.
-   `gl.RENDERBUFFER_DEPTH_SIZE`: Returns a [`GLint`](../webgl_api/types) that is the resolution size (in bits) for the depth component.
-   `gl.RENDERBUFFER_STENCIL_SIZE`: Returns a [`GLint`](../webgl_api/types) that is the resolution size (in bits) for the stencil component.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following value is available additionally:
    -   `gl.RENDERBUFFER_SAMPLES`: Returns a [`GLint`](../webgl_api/types) indicating the number of samples of the image of the currently bound renderbuffer.

### Return value

Depends on the requested information (as specified with `pname`). Either a [`GLint`](../webgl_api/types) or a [`GLenum`](../webgl_api/types).

Examples
--------

    gl.getRenderbufferParameter(gl.RENDERBUFFER, gl.RENDERBUFFER_WIDTH);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.7">WebGL 1.0<br />
<span class="small">The definition of 'getRenderbufferParameter' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetRenderbufferParameteriv.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetRenderbufferParameteriv' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.5">WebGL 2.0<br />
<span class="small">The definition of 'getRenderbufferParameter' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL 2.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetRenderbufferParameteriv.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetRenderbufferParameteriv' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3 API.<br />
<br />
Adds a new <code>pname</code> value:<br />
<code>gl.RENDERBUFFER_SAMPLES</code></td></tr></tbody></table>

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

`getRenderbufferParameter`

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
-   [`WebGLRenderingContext.renderbufferStorage()`](renderbufferstorage)
-   Other buffers: [`WebGLBuffer`](../webglbuffer), [`WebGLFramebuffer`](../webglframebuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getRenderbufferParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getRenderbufferParameter</a>
