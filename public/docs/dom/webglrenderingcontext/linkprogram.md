WebGLRenderingContext.linkProgram()
===================================

The [`WebGLRenderingContext`](../webglrenderingcontext) interface's `linkProgram()` method links a given [`WebGLProgram`](../webglprogram), completing the process of preparing the GPU code for the program's fragment and vertex shaders.

Syntax
------

    void gl.linkProgram(program);

### Parameters

`program`  
The [`WebGLProgram`](../webglprogram) to link.

### Return value

None.

Examples
--------

    var program = gl.createProgram();

    // Attach pre-existing shaders
    gl.attachShader(program, vertexShader);
    gl.attachShader(program, fragmentShader);

    gl.linkProgram(program);

    if ( !gl.getProgramParameter( program, gl.LINK_STATUS) ) {
      var info = gl.getProgramInfoLog(program);
      throw new Error('Could not compile WebGL program. \n\n' + info);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'linkProgram' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glLinkProgram.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glLinkProgram' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`linkProgram`

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
-   [`WebGLRenderingContext.useProgram()`](useprogram)
-   [`WebGLRenderingContext.validateProgram()`](validateprogram)
-   [`WebGLRenderingContext.getProgramParameter()`](getprogramparameter)
-   [`WebGLRenderingContext.getProgramInfoLog()`](getprograminfolog)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/linkProgram" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/linkProgram</a>
