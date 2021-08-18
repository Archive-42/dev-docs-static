WebGLRenderingContext.bindTexture()
===================================

The `WebGLRenderingContext.bindTexture()` method of the [WebGL API](../webgl_api) binds a given [`WebGLTexture`](../webgltexture) to a target (binding point).

Syntax
------

    void gl.bindTexture(target, texture);

### Parameters

target  
A [`GLenum`](../webgl_api/types) specifying the binding point (target). Possible values:

-   `gl.TEXTURE_2D`: A two-dimensional texture.
-   `gl.TEXTURE_CUBE_MAP`: A cube-mapped texture.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.TEXTURE_3D`: A three-dimensional texture.
    -   `gl.TEXTURE_2D_ARRAY`: A two-dimensional array texture.

texture  
A [`WebGLTexture`](../webgltexture) object to bind.

### Return value

None.

### Exceptions

A `gl.INVALID_ENUM` error is thrown if `target` is not `gl.TEXTURE_2D`, `gl.TEXTURE_CUBE_MAP`, `gl.TEXTURE_3D`, or `gl.TEXTURE_2D_ARRAY`.

Examples
--------

### Binding a texture

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var texture = gl.createTexture();

    gl.bindTexture(gl.TEXTURE_2D, texture);

### Getting current bindings

To check the current texture binding, query the `gl.TEXTURE_BINDING_2D` or `gl.TEXTURE_BINDING_CUBE_MAP` constants.

    gl.getParameter(gl.TEXTURE_BINDING_2D);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.8">WebGL 1.0<br />
<span class="small">The definition of 'bindTexture' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glBindTexture.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glBindTexture' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2.0 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.1">WebGL 2.0<br />
<span class="small">The definition of 'bindTexture' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL 2.<br />
Adds: <code>gl.TEXTURE_3D</code> and <code>gl.TEXTURE_2D_ARRAY</code></td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBindTexture.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBindTexture' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`bindTexture`

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
-   [`WebGLRenderingContext.deleteTexture()`](deletetexture)
-   [`WebGLRenderingContext.isTexture()`](istexture)
-   [`WebGLRenderingContext.texImage2D()`](teximage2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bindTexture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bindTexture</a>
