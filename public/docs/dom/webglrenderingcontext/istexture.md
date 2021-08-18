WebGLRenderingContext.isTexture()
=================================

The `WebGLRenderingContext.isTexture()` method of the [WebGL API](../webgl_api) returns `true` if the passed [`WebGLTexture`](../webgltexture) is valid and `false` otherwise.

Syntax
------

    GLboolean gl.isTexture(texture);

### Parameters

texture  
A [`WebGLTexture`](../webgltexture) to check.

### Return value

A [`GLboolean`](../webgl_api/types) indicating whether or not the texture is valid.

Examples
--------

### Checking a texture

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var texture = gl.createTexture();

    gl.isTexture(texture);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.8">WebGL 1.0<br />
<span class="small">The definition of 'isTexture' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glIsTexture.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glIsTexture' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`isTexture`

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

-   [`WebGLRenderingContext.bindTexture()`](bindtexture)
-   [`WebGLRenderingContext.createTexture()`](createtexture)
-   [`WebGLRenderingContext.deleteTexture()`](deletetexture)
-   [`WebGLRenderingContext.texImage2D()`](teximage2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/isTexture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/isTexture</a>
