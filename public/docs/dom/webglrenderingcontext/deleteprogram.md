WebGLRenderingContext.deleteProgram()
=====================================

The `WebGLRenderingContext.deleteProgram()` method of the [WebGL API](../webgl_api) deletes a given [`WebGLProgram`](../webglprogram) object. This method has no effect if the program has already been deleted.

Syntax
------

    void gl.deleteProgram(program);

### Parameters

`program`  
A [`WebGLProgram`](../webglprogram) object to delete.

### Return value

None.

Examples
--------

### Deleting a program

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var program = gl.createProgram();

    // ...

    gl.deleteProgram(program);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'deleteProgram' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glDeleteProgram.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDeleteProgram' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`deleteProgram`

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

-   [`WebGLRenderingContext.createProgram()`](createprogram)
-   [`WebGLRenderingContext.isProgram()`](isprogram)
-   [`WebGLRenderingContext.linkProgram()`](linkprogram)
-   [`WebGLRenderingContext.useProgram()`](useprogram)
-   [`WebGLRenderingContext.validateProgram()`](validateprogram)
-   [`WebGLRenderingContext.getProgramParameter()`](getprogramparameter)
-   [`WebGLRenderingContext.getProgramInfoLog()`](getprograminfolog)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/deleteProgram" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/deleteProgram</a>
