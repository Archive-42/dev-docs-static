WebGLRenderingContext.copyTexSubImage2D()
=========================================

The `WebGLRenderingContext.copyTexSubImage2D()` method of the [WebGL API](../webgl_api) copies pixels from the current [`WebGLFramebuffer`](../webglframebuffer) into an existing 2D texture sub-image.

Syntax
------

    void gl.copyTexSubImage2D(target, level, xoffset, yoffset, x, y, width, height);

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
A [`GLint`](../webgl_api/types) specifying the horizontal offset within the texture image.

`yoffset`  
A [`GLint`](../webgl_api/types) specifying the vertical offset within the texture image.

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

    gl.copyTexSubImage2D(gl.TEXTURE_2D, 0, 0,0, 0, 0, 16, 16);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.8">WebGL 1.0<br />
<span class="small">The definition of 'copyTexSubImage2D' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glCopyTexSubImage2D.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glCopyTexSubImage2D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`copyTexSubImage2D`

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

See also
--------

-   [`WebGLRenderingContext.copyTexImage2D()`](copyteximage2d)
-   [`WebGLRenderingContext.texImage2D()`](teximage2d)
-   [`WebGLRenderingContext.texSubImage2D()`](texsubimage2d)
-   [`WebGLRenderingContext.compressedTexImage2D()`](compressedteximage2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/copyTexSubImage2D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/copyTexSubImage2D</a>
