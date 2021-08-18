WebGLRenderingContext.detachShader()
====================================

The **WebGLRenderingContext.detachShader()** method of the [WebGL API](../webgl_api) detaches a previously attached [`WebGLShader`](../webglshader) from a [`WebGLProgram`](../webglprogram).

Syntax
------

    void gl.detachShader(program, shader);

### Parameters

`program`  
A [`WebGLProgram`](../webglprogram).

`shader`  
A fragment or vertex [`WebGLShader`](../webglshader).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'detachShader' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glDetachShader.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDetachShader' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>OpenGL man page.</td></tr></tbody></table>

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

`detachShader`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/detachShader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/detachShader</a>
