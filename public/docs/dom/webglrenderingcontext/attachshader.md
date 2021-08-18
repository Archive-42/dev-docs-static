WebGLRenderingContext.attachShader()
====================================

The **WebGLRenderingContext.attachShader()** method of the [WebGL API](../webgl_api) attaches either a fragment or vertex [`WebGLShader`](../webglshader) to a [`WebGLProgram`](../webglprogram).

Syntax
------

    void gl.attachShader(program, shader);

### Parameters

`program`  
A [`WebGLProgram`](../webglprogram).

`shader`  
A fragment or vertex [`WebGLShader`](../webglshader).

Examples
--------

The following code attaches pre-existing shaders to a [`WebGLProgram`](../webglprogram).

    var program = gl.createProgram();

    // Attach pre-existing shaders
    gl.attachShader(program, vertexShader);
    gl.attachShader(program, fragmentShader);

    gl.linkProgram(program);

    if ( !gl.getProgramParameter( program, gl.LINK_STATUS) ) {
      var info = gl.getProgramInfoLog(program);
      throw 'Could not compile WebGL program. \n\n' + info;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'attachShader' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glAttachShader.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glAttachShader' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>OpenGL man page.</td></tr></tbody></table>

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

`attachShader`

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

-   [`WebGLProgram`](../webglprogram)
-   [`WebGLShader`](../webglshader)
-   [`WebGLRenderingContext.attachShader()`](attachshader)
-   [`WebGLRenderingContext.compileShader()`](compileshader)
-   [`WebGLRenderingContext.createProgram()`](createprogram)
-   [`WebGLRenderingContext.createShader()`](createshader)
-   [`WebGLRenderingContext.deleteProgram()`](deleteprogram)
-   [`WebGLRenderingContext.deleteShader()`](deleteshader)
-   [`WebGLRenderingContext.detachShader()`](detachshader)
-   [`WebGLRenderingContext.getAttachedShaders()`](getattachedshaders)
-   [`WebGLRenderingContext.getProgramParameter()`](getprogramparameter)
-   [`WebGLRenderingContext.getProgramInfoLog()`](getprograminfolog)
-   [`WebGLRenderingContext.getShaderParameter()`](getshaderparameter)
-   [`WebGLRenderingContext.getShaderPrecisionFormat()`](getshaderprecisionformat)
-   [`WebGLRenderingContext.getShaderInfoLog()`](getshaderinfolog)
-   [`WebGLRenderingContext.getShaderSource()`](getshadersource)
-   [`WebGLRenderingContext.isProgram()`](isprogram)
-   [`WebGLRenderingContext.isShader()`](isshader)
-   [`WebGLRenderingContext.linkProgram()`](linkprogram)
-   [`WebGLRenderingContext.shaderSource()`](shadersource)
-   [`WebGLRenderingContext.useProgram()`](useprogram)
-   [`WebGLRenderingContext.validateProgram()`](validateprogram)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/attachShader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/attachShader</a>
