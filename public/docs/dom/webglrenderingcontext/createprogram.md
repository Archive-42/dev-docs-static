WebGLRenderingContext.createProgram()
=====================================

The `WebGLRenderingContext.createProgram()` method of the [WebGL API](../webgl_api) creates and initializes a [`WebGLProgram`](../webglprogram) object.

Syntax
------

    WebGLProgram gl.createProgram();

### Parameters

None.

### Return value

A [`WebGLProgram`](../webglprogram) object that is a combination of two compiled [`WebGLShader`](../webglshader)s consisting of a vertex shader and a fragment shader (both written in GLSL). These are then linked into a usable program..

Examples
--------

### Creating a WebGL program

    var program = gl.createProgram();

    // Attach pre-existing shaders
    gl.attachShader(program, vertexShader);
    gl.attachShader(program, fragmentShader);

    gl.linkProgram(program);

    if ( !gl.getProgramParameter( program, gl.LINK_STATUS) ) {
      var info = gl.getProgramInfoLog(program);
      throw 'Could not compile WebGL program. \n\n' + info;
    }

See [`WebGLShader`](../webglshader) for information on creating the `vertexShader` and `fragmentShader` in the above example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'createProgram' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glCreateProgram.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glCreateProgram' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`createProgram`

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

-   [`WebGLRenderingContext.deleteProgram()`](deleteprogram)
-   [`WebGLRenderingContext.isProgram()`](isprogram)
-   [`WebGLRenderingContext.linkProgram()`](linkprogram)
-   [`WebGLRenderingContext.useProgram()`](useprogram)
-   [`WebGLRenderingContext.validateProgram()`](validateprogram)
-   [`WebGLRenderingContext.getProgramParameter()`](getprogramparameter)
-   [`WebGLRenderingContext.getProgramInfoLog()`](getprograminfolog)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/createProgram" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/createProgram</a>
