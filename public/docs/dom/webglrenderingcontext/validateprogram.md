WebGLRenderingContext.validateProgram()
=======================================

The `WebGLRenderingContext.validateProgram()` method of the [WebGL API](../webgl_api) validates a [`WebGLProgram`](../webglprogram). It checks if it is successfully linked and if it can be used in the current WebGL state.

Syntax
------

    void gl.validateProgram(program);

### Parameters

program  
A [`WebGLProgram`](../webglprogram) to validate.

### Return value

None.

Examples
--------

    var program = gl.createProgram();

    // Attach pre-existing shaders
    gl.attachShader(program, vertexShader);
    gl.attachShader(program, fragmentShader);

    gl.linkProgram(program);
    gl.validateProgram(program);

    if ( !gl.getProgramParameter( program, gl.LINK_STATUS) ) {
      var info = gl.getProgramInfoLog(program);
      throw 'Could not compile WebGL program. \n\n' + info;
    }

    gl.useProgram(program);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'validateProgram' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glValidateProgram.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glValidateProgram' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`validateProgram`

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
-   [`WebGLRenderingContext.useProgram()`](useprogram)
-   [`WebGLRenderingContext.getProgramParameter()`](getprogramparameter)
-   [`WebGLRenderingContext.getProgramInfoLog()`](getprograminfolog)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/validateProgram" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/validateProgram</a>
