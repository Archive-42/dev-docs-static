WebGLRenderingContext.generateMipmap()
======================================

The `WebGLRenderingContext.generateMipmap()` method of the [WebGL API](../webgl_api) generates a set of mipmaps for a [`WebGLTexture`](../webgltexture) object.

Mipmaps are used to create distance with objects. A higher-resolution mipmap is used for objects that are closer, and a lower-resolution mipmap is used for objects that are farther away. It starts with the resolution of the texture image and halves the resolution until a 1x1 dimension texture image is created.

Syntax
------

    void gl.generateMipmap(target);

### Parameters

target  
A [`GLenum`](../webgl_api/types) specifying the binding point (target) of the active texture whose mipmaps will be generated. Possible values:

-   `gl.TEXTURE_2D`: A two-dimensional texture.
-   `gl.TEXTURE_CUBE_MAP`: A cube-mapped texture.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.TEXTURE_3D`: A three-dimensional texture.
    -   `gl.TEXTURE_2D_ARRAY`: A two-dimensional array texture.

### Return value

None.

Examples
--------

    gl.generateMipmap(gl.TEXTURE_2D);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.8">WebGL 1.0<br />
<span class="small">The definition of 'generateMipmap' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGenerateMipmap.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGenerateMipmap' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2.0 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGenerateMipmap.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGenerateMipmap' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.<br />
Adds: <code>gl.TEXTURE_3D</code> and <code>gl.TEXTURE_2D_ARRAY</code></td></tr></tbody></table>

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

`generateMipmap`

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
-   [`WebGLRenderingContext.getTexParameter()`](gettexparameter)
-   [`WebGLRenderingContext.texParameterf()`](texparameter)
-   [`WebGLRenderingContext.texParameteri()`](texparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/generateMipmap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/generateMipmap</a>
