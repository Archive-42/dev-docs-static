WebGL2RenderingContext.copyTexSubImage3D()
==========================================

The `WebGL2RenderingContext.copyTexSubImage3D()` method of the [WebGL API](../webgl_api) copies pixels from the current [`WebGLFramebuffer`](../webglframebuffer) into an existing 3D texture sub-image.

Syntax
------

    void gl.copyTexSubImage3D(target, level, xoffset, yoffset, zoffset, x, y, width, height);

### Parameters

`target`  
A [`GLenum`](../webgl_api/types) specifying the binding point (target) of the active texture. Possible values:

-   `gl.TEXTURE_3D`: A three-dimensional texture.
-   `gl.TEXTURE_2D_ARRAY`: A two-dimensional array texture.

`level`  
A [`GLint`](../webgl_api/types) specifying the level of detail. Level 0 is the base image level and level *n* is the *n*th mipmap reduction level.

`xoffset`  
A [`GLint`](../webgl_api/types) specifying the x offset within the texture image.

`yoffset`  
A [`GLint`](../webgl_api/types) specifying the y offset within the texture image.

`zoffset`  
A [`GLint`](../webgl_api/types) specifying the z offset within the texture image.

`x`  
A [`GLint`](../webgl_api/types) specifying the x coordinate of the lower left corner where to start copying.

`y`  
A [`GLint`](../webgl_api/types) specifying the y coordinate of the lower left corner where to start copying.

`width`  
A [`GLsizei`](../webgl_api/types) specifying the width of the texture.

`height`  
A [`GLsizei`](../webgl_api/types) specifying the height of the texture.

### Return value

None.

Examples
--------

    gl.copyTexSubImage3D(gl.TEXTURE_3D, 0, 0, 0, 0, 0, 0, 16, 16);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.6">WebGL 2.0<br />
<span class="small">The definition of 'copyTexSubImage3D' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glCopyTexSubImage3D.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glCopyTexSubImage3D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`copyTexSubImage3D`

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
-   [`WebGLRenderingContext.texImage2D()`](../webglrenderingcontext/teximage2d)
-   [`WebGLRenderingContext.texSubImage2D()`](../webglrenderingcontext/texsubimage2d)
-   [`WebGLRenderingContext.compressedTexImage2D()`](../webglrenderingcontext/compressedteximage2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/copyTexSubImage3D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/copyTexSubImage3D</a>
