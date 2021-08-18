WebGLRenderingContext.isProgram()
=================================

The `WebGLRenderingContext.isProgram()` method of the [WebGL API](../webgl_api) returns `true` if the passed [`WebGLProgram`](../webglprogram) is valid, `false` otherwise.

Syntax
------

    GLboolean gl.isProgram(program);

### Parameters

program  
A [`WebGLProgram`](../webglprogram) to check.

### Return value

A [`GLboolean`](../webgl_api/types) indicating whether or not the program is valid.

Examples
--------

### Checking a program

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var program = gl.createProgram();

    // ...

    gl.isProgram(program);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'isProgram' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glIsProgram.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glIsProgram' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`isProgram`

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
-   [`WebGLRenderingContext.deleteProgram()`](deleteprogram)
-   [`WebGLRenderingContext.linkProgram()`](linkprogram)
-   [`WebGLRenderingContext.useProgram()`](useprogram)
-   [`WebGLRenderingContext.validateProgram()`](validateprogram)
-   [`WebGLRenderingContext.getProgramParameter()`](getprogramparameter)
-   [`WebGLRenderingContext.getProgramInfoLog()`](getprograminfolog)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/isProgram" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/isProgram</a>
