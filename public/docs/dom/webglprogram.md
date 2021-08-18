WebGLProgram
============

The `WebGLProgram` is part of the [WebGL API](webgl_api) and is a combination of two compiled [`WebGLShader`](webglshader)s consisting of a vertex shader and a fragment shader (both written in GLSL). To create a `WebGLProgram`, call the GL context's [`createProgram()`](webglrenderingcontext/createprogram) function. After attaching the shader programs using [`attachShader()`](webglrenderingcontext/attachshader), you link them into a usable program. This is shown in the code below.

    var program = gl.createProgram();

    // Attach pre-existing shaders
    gl.attachShader(program, vertexShader);
    gl.attachShader(program, fragmentShader);

    gl.linkProgram(program);

    if ( !gl.getProgramParameter( program, gl.LINK_STATUS) ) {
      var info = gl.getProgramInfoLog(program);
      throw 'Could not compile WebGL program. \n\n' + info;
    }

See [`WebGLShader`](webglshader) for information on creating the `vertexShader` and `fragmentShader` in the above example.

Examples
--------

### Using the program

The steps to actually do some work with the program involve telling the GPU to use the program, bind the appropriate data and configuration options, and finally draw something to the screen.

    // Use the program
    gl.useProgram(program);

    // Bind existing attribute data
    gl.bindBuffer(gl.ARRAY_BUFFER, buffer);
    gl.enableVertexAttribArray(attributeLocation);
    gl.vertexAttribPointer(attributeLocation, 3, gl.FLOAT, false, 0, 0);

    // Draw a single triangle
    gl.drawArrays(gl.TRIANGLES, 0, 3);

### Deleting the program

If there is an error linking the program or you wish to delete an existing program, then it is as simple as running [`WebGLRenderingContext.deleteProgram()`](webglrenderingcontext/deleteprogram). This frees the memory of the linked program.

    gl.deleteProgram(program);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.6">WebGL 1.0<br />
<span class="small">The definition of 'WebGLProgram' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLProgram`

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

`worker_support`

No

No

44

No

No

No

No

No

No

No

No

No

See also
--------

-   [`WebGLShader`](webglshader)
-   [`WebGLRenderingContext.attachShader()`](webglrenderingcontext/attachshader)
-   [`WebGLRenderingContext.compileShader()`](webglrenderingcontext/compileshader)
-   [`WebGLRenderingContext.createProgram()`](webglrenderingcontext/createprogram)
-   [`WebGLRenderingContext.createShader()`](webglrenderingcontext/createshader)
-   [`WebGLRenderingContext.deleteProgram()`](webglrenderingcontext/deleteprogram)
-   [`WebGLRenderingContext.deleteShader()`](webglrenderingcontext/deleteshader)
-   [`WebGLRenderingContext.detachShader()`](webglrenderingcontext/detachshader)
-   [`WebGLRenderingContext.getAttachedShaders()`](webglrenderingcontext/getattachedshaders)
-   [`WebGLRenderingContext.getProgramParameter()`](webglrenderingcontext/getprogramparameter)
-   [`WebGLRenderingContext.getProgramInfoLog()`](webglrenderingcontext/getprograminfolog)
-   [`WebGLRenderingContext.getShaderParameter()`](webglrenderingcontext/getshaderparameter)
-   [`WebGLRenderingContext.getShaderPrecisionFormat()`](webglrenderingcontext/getshaderprecisionformat)
-   [`WebGLRenderingContext.getShaderInfoLog()`](webglrenderingcontext/getshaderinfolog)
-   [`WebGLRenderingContext.getShaderSource()`](webglrenderingcontext/getshadersource)
-   [`WebGLRenderingContext.isProgram()`](webglrenderingcontext/isprogram)
-   [`WebGLRenderingContext.isShader()`](webglrenderingcontext/isshader)
-   [`WebGLRenderingContext.linkProgram()`](webglrenderingcontext/linkprogram)
-   [`WebGLRenderingContext.shaderSource()`](webglrenderingcontext/shadersource)
-   [`WebGLRenderingContext.useProgram()`](webglrenderingcontext/useprogram)
-   [`WebGLRenderingContext.validateProgram()`](webglrenderingcontext/validateprogram)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLProgram" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLProgram</a>
