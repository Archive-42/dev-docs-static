WebGLRenderingContext.getProgramInfoLog()
=========================================

The **WebGLRenderingContext.getProgramInfoLog** returns the information log for the specified [`WebGLProgram`](../webglprogram) object. It contains errors that occurred during failed linking or validation of `WebGLProgram` objects.

Syntax
------

    gl.getProgramInfoLog(program);

### Parameters

`program`  
The [`WebGLProgram`](../webglprogram) to query.

### Return value

A [`DOMString`](../domstring) that contains diagnostic messages, warning messages, and other information about the last linking or validation operation. When a [`WebGLProgram`](../webglprogram) object is initially created, its information log will be a string of length 0.

Examples
--------

### Checking program errors

    var program = gl.createProgram();

    // Attach pre-existing shaders
    gl.attachShader(program, vertexShader);
    gl.attachShader(program, fragmentShader);

    gl.linkProgram(program);

    gl.getProgramInfoLog(program);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'getProgramInfoLog' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetProgramInfoLog.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetProgramInfoLog' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`getProgramInfoLog`

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

-   [`WebGLRenderingContext.getShaderInfoLog()`](getshaderinfolog)
-   [`WebGLRenderingContext.getError()`](geterror)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getProgramInfoLog" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getProgramInfoLog</a>
