Hello GLSL
==========

### Hello World program in GLSL

-   <a href="raining_rectangles" class="button minimal">« Previous</a>
-   <a href="hello_vertex_attributes" class="button minimal">Next »</a>

This WebGL example demonstrates a very basic GLSL shader program that draws a solid color square.

**Note**: This example will most likely work in all modern desktop browsers. But it may not work in some mobile or older browsers. If the canvas remains blank, you can check the output of the next example, which draws exactly the same thing. But remember to read through the explanations and code on this page, before moving on to the next.

A very simple first shader program.

    <script type="x-shader/x-vertex" id="vertex-shader">
    #version 100
    void main() {
      gl_Position = vec4(0.0, 0.0, 0.0, 1.0);
      gl_PointSize = 64.0;
    }
    </script>

    <script type="x-shader/x-fragment" id="fragment-shader">
    #version 100
    void main() {
      gl_FragColor = vec4(0.18, 0.54, 0.34, 1.0);
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
      gl.vertexAttribPointer(0, 1, gl.FLOAT, false, 0, 0);
    }

    function cleanup() {
    gl.useProgram(null);
    if (buffer)
      gl.deleteBuffer(buffer);
    if (program)
      gl.deleteProgram(program);
    }

The source code of this example is also available on [GitHub](https://github.com/idofilin/webgl-by-example/tree/master/hello-glsl).

-   <a href="raining_rectangles" class="button minimal">« Previous</a>
-   <a href="hello_vertex_attributes" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Hello_GLSL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Hello_GLSL</a>
