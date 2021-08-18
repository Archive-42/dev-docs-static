Textures from code
==================

### Drawing textures with code

-   <a href="hello_vertex_attributes" class="button minimal">« Previous</a>
-   <a href="video_textures" class="button minimal">Next »</a>

This WebGL example provides a simple demonstration of procedural texturing with fragment shaders. That is, using code to generate textures for use in shading WebGL objects.

Texturing a point sprite with calculations done per-pixel in the fragment shader.

    <script type="x-shader/x-vertex" id="vertex-shader">
    #version 100
    precision highp float;

    attribute vec2 position;

    void main() {
      gl_Position = vec4(position, 0.0, 1.0);
      gl_PointSize = 128.0;
    }
    </script>

    <script type="x-shader/x-fragment" id="fragment-shader">
    #version 100
    precision mediump float;
    void main() {
      vec2 fragmentPosition = 2.0*gl_PointCoord - 1.0;
      float distance = length(fragmentPosition);
      float distanceSqrd = distance * distance;
      gl_FragColor = vec4(
        0.2/distanceSqrd,
        0.1/distanceSqrd,
        0.0, 1.0 );
    }
    </script>

    "use strict"
    window.addEventListener("load", setupWebGL, false);
    var gl,
      program;
    function setupWebGL (evt) {
      window.removeEventListener(evt.type, setupWebGL, false);
      if (!(gl = getRenderingContext()))
        return;

      var source = document.querySelector("#vertex-shader").innerHTML;
      var vertexShader = gl.createShader(gl.VERTEX_SHADER);
      gl.shaderSource(vertexShader,source);
      gl.compileShader(vertexShader);
      source = document.querySelector("#fragment-shader").innerHTML
      var fragmentShader = gl.createShader(gl.FRAGMENT_SHADER);
      gl.shaderSource(fragmentShader,source);
      gl.compileShader(fragmentShader);
      program = gl.createProgram();
      gl.attachShader(program, vertexShader);
      gl.attachShader(program, fragmentShader);
      gl.linkProgram(program);
      gl.detachShader(program, vertexShader);
      gl.detachShader(program, fragmentShader);
      gl.deleteShader(vertexShader);
      gl.deleteShader(fragmentShader);
      if (!gl.getProgramParameter(program, gl.LINK_STATUS)) {
        var linkErrLog = gl.getProgramInfoLog(program);
        cleanup();
        document.querySelector("p").innerHTML =
          "Shader program did not link successfully. "
          + "Error log: " + linkErrLog;
        return;
      }
      initializeAttributes();
      gl.useProgram(program);
      gl.drawArrays(gl.POINTS, 0, 1);
      cleanup();
    }

    var buffer;
    function initializeAttributes() {
      gl.enableVertexAttribArray(0);
      buffer = gl.createBuffer();
      gl.bindBuffer(gl.ARRAY_BUFFER, buffer);
      gl.bufferData(gl.ARRAY_BUFFER, new Float32Array([0.0, 0.0]), gl.STATIC_DRAW);
      gl.vertexAttribPointer(0, 2, gl.FLOAT, false, 0, 0);
    }

    function cleanup() {
    gl.useProgram(null);
    if (buffer)
      gl.deleteBuffer(buffer);
    if (program)
      gl.deleteProgram(program);
    }

The source code of this example is also available on [GitHub](https://github.com/idofilin/webgl-by-example/tree/master/textures-from-code).

-   <a href="hello_vertex_attributes" class="button minimal">« Previous</a>
-   <a href="video_textures" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Textures_from_code" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Textures_from_code</a>
