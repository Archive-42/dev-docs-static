WebGL2RenderingContext.readBuffer()
===================================

The `WebGL2RenderingContext.readBuffer()` method of the [WebGL 2 API](../webgl_api) selects a color buffer as the source for pixels for subsequent calls to [`copyTexImage2D`](../webglrenderingcontext/copyteximage2d), [`copyTexSubImage2D`](../webglrenderingcontext/copytexsubimage2d), [`copyTexSubImage3D`](copytexsubimage3d) or [`readPixels`](../webglrenderingcontext/readpixels).

Syntax
------

    void gl.readBuffer(src);

### Parameters

`src`  
A [`GLenum`](../webgl_api/types) specifying a color buffer. Possible values:

-   `gl.BACK`: Reads from the back color buffer.
-   `gl.NONE`: Reads from no color buffer.
-   `gl.COLOR_ATTACHMENT{0-15}`: Reads from one of the 16 color attachment buffers.

### Return value

None.

Examples
--------

    gl.readBuffer(gl.COLOR_ATTACHMENT0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.4">WebGL 2.0<br />
<span class="small">The definition of 'readBuffer' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glReadBuffer.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glReadBuffer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`readBuffer`

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

-   [`WebGLRenderingContext.copyTexImage2D()`](../webglrenderingcontext/copyteximage2d)
-   [`WebGLRenderingContext.copyTexSubImage2D()`](../webglrenderingcontext/copytexsubimage2d)
-   [`WebGL2RenderingContext.copyTexSubImage3D()`](copytexsubimage3d)
-   [`WebGLRenderingContext.readPixels()`](../webglrenderingcontext/readpixels)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/readBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/readBuffer</a>
