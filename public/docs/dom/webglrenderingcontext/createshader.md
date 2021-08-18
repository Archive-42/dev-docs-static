WebGLRenderingContext.createShader()
====================================

The [`WebGLRenderingContext`](../webglrenderingcontext) method `createShader()` of the [WebGL API](../webgl_api) creates a [`WebGLShader`](../webglshader) that can then be configured further using [`WebGLRenderingContext.shaderSource()`](shadersource) and [`WebGLRenderingContext.compileShader()`](compileshader).

Syntax
------

    WebGLShader gl.createShader(type);

### Parameters

`type`  
Either `gl.VERTEX_SHADER` or `gl.FRAGMENT_SHADER`

Examples
--------

See [`WebGLShader`](../webglshader) for usage and examples.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'createShader' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glCreateShader.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glCreateShader' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>OpenGL man page.</td></tr></tbody></table>

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

`createShader`

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
-   [`WebGLRenderingContext.bindAttribLocation()`](bindattriblocation)
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/createShader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/createShader</a>
