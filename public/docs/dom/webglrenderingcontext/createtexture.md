WebGLRenderingContext.createTexture()
=====================================

The `WebGLRenderingContext.createTexture()` method of the [WebGL API](../webgl_api) creates and initializes a [`WebGLTexture`](../webgltexture) object.

Syntax
------

    WebGLTexture gl.createTexture();

### Parameters

None.

### Return value

A [`WebGLTexture`](../webgltexture) object to which images can be bound to.

Examples
--------

See also the [WebGL tutorial](../webgl_api/tutorial) on [Using textures in WebGL](../webgl_api/tutorial/using_textures_in_webgl).

### Creating a texture

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var texture = gl.createTexture();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.8">WebGL 1.0<br />
<span class="small">The definition of 'createTexture' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGenTextures.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGenTextures' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`createTexture`

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
-   [`WebGLRenderingContext.deleteTexture()`](deletetexture)
-   [`WebGLRenderingContext.isTexture()`](istexture)
-   [`WebGLRenderingContext.texImage2D()`](teximage2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/createTexture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/createTexture</a>
