WebGLShader
===========

The **WebGLShader** is part of the [WebGL API](webgl_api) and can either be a vertex or a fragment shader. A [`WebGLProgram`](webglprogram) requires both types of shaders.

Description
-----------

To create a **WebGLShader** use [`WebGLRenderingContext.createShader`](webglrenderingcontext/createshader), then hook up the GLSL source code using [`WebGLRenderingContext.shaderSource()`](webglrenderingcontext/shadersource), and finally invoke [`WebGLRenderingContext.compileShader()`](webglrenderingcontext/compileshader) to finish and compile the shader. At this point the **WebGLShader** is still not in a usable form and must still be attached to a [`WebGLProgram`](webglprogram).

    function createShader (gl, sourceCode, type) {
      // Compiles either a shader of type gl.VERTEX_SHADER or gl.FRAGMENT_SHADER
      var shader = gl.createShader( type );
      gl.shaderSource( shader, sourceCode );
      gl.compileShader( shader );

      if ( !gl.getShaderParameter(shader, gl.COMPILE_STATUS) ) {
        var info = gl.getShaderInfoLog( shader );
        throw 'Could not compile WebGL program. \n\n' + info;
      }
      return shader;
    }

See [`WebGLProgram`](webglprogram) for information on attaching the shaders.

Examples
--------

### Creating a vertex shader

Note that there are many other strategies for writing and accessing shader source code strings. These example are for illustration purposes only.

    var vertexShaderSource =
      'attribute vec4 position;\n' +
      'void main() {\n' +
      '  gl_Position = position;\n' +
      '}\n';

    //Use the createShader function from the example above
    var vertexShader = createShader(gl, vertexShaderSource, gl.VERTEX_SHADER)

### Creating a fragment shader

    var fragmentShaderSource =
      'void main() {\n' +
      '  gl_FragColor = vec4(1.0, 1.0, 1.0, 1.0);\n' +
      '}\n';

    //Use the createShader function from the example above
    var fragmentShader = createShader(gl, fragmentShaderSource, gl.FRAGMENT_SHADER)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.8">WebGL 1.0<br />
<span class="small">The definition of 'WebGLShader' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLShader`

9

12

4

11

12

5.1

Yes

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

-   [`WebGLProgram`](webglprogram)
-   [`WebGLRenderingContext.attachShader()`](webglrenderingcontext/attachshader)
-   [`WebGLRenderingContext.bindAttribLocation()`](webglrenderingcontext/bindattriblocation)
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLShader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLShader</a>
