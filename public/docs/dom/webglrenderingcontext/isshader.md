WebGLRenderingContext.isShader()
================================

The `WebGLRenderingContext.isShader()` method of the [WebGL API](../webgl_api) returns `true` if the passed [`WebGLShader`](../webglshader) is valid, `false` otherwise.

Syntax
------

    GLboolean gl.isShader(shader);

### Parameters

shader  
A [`WebGLShader`](../webglshader) to check.

### Return value

A [`GLboolean`](../webgl_api/types) indicating whether or not the shader is valid.

Examples
--------

### Checking a shader

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var shader = gl.createShader(gl.VERTEX_SHADER);

    // ...

    gl.isShader(shader);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'isShader' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glIsShader.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glIsShader' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`isShader`

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
-   [`WebGLRenderingContext.deleteShader()`](deleteshader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/isShader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/isShader</a>
