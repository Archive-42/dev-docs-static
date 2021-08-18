WebGLRenderingContext.deleteShader()
====================================

The `WebGLRenderingContext.deleteShader()` method of the [WebGL API](../webgl_api) marks a given [`WebGLShader`](../webglshader) object for deletion. It will then be deleted whenever the shader is no longer in use. This method has no effect if the shader has already been deleted, and the [`WebGLShader`](../webglshader) is automatically marked for deletion when it is destroyed by the garbage collector.

Syntax
------

    void gl.deleteShader(shader);

### Parameters

shader  
A [`WebGLShader`](../webglshader) object to delete.

### Return value

None.

Examples
--------

### Deleting a shader

    gl.deleteShader(shader);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'deleteShader' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glDeleteShader.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDeleteShader' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`deleteShader`

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

-   [`WebGLRenderingContext.createShader()`](createshader)
-   [`WebGLRenderingContext.isShader()`](isshader)
-   [`WebGLRenderingContext.getAttachedShaders()`](getattachedshaders)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/deleteShader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/deleteShader</a>
