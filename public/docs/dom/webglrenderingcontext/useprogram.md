WebGLRenderingContext.useProgram()
==================================

The `WebGLRenderingContext.useProgram()` method of the [WebGL API](../webgl_api) sets the specified [`WebGLProgram`](../webglprogram) as part of the current rendering state.

Syntax
------

    void gl.useProgram(program);

### Parameters

program  
A [`WebGLProgram`](../webglprogram) to use.

### Return value

None.

Examples
--------

    var program = gl.createProgram();

    // Attach pre-existing shaders
    gl.attachShader(program, vertexShader);
    gl.attachShader(program, fragmentShader);

    gl.linkProgram(program);
    gl.useProgram(program);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'useProgram' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glUseProgram.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glUseProgram' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`useProgram`

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
-   [`WebGLRenderingContext.isProgram()`](isprogram)
-   [`WebGLRenderingContext.linkProgram()`](linkprogram)
-   [`WebGLRenderingContext.validateProgram()`](validateprogram)
-   [`WebGLRenderingContext.getProgramParameter()`](getprogramparameter)
-   [`WebGLRenderingContext.getProgramInfoLog()`](getprograminfolog)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/useProgram" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/useProgram</a>
