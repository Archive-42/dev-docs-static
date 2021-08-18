Canvas size and WebGL
=====================

### Effect of canvas size on rendering with WebGL

-   <a href="basic_scissoring" class="button minimal">« Previous</a>
-   <a href="boilerplate_1" class="button minimal">Next »</a>

This WebGL example explores the effect of setting (or not setting) the canvas size to its element size in [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) pixels, as it appears in the browser window.

With [`scissor()`](../../webglrenderingcontext/scissor) and [`clear()`](../../webglrenderingcontext/clear) we can demonstrate how the WebGL drawing buffer is affected by the size of the canvas.

The size of the first canvas is set to the styled [`Element`](../../element) size, determined by [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS). This is done by assigning the [`width`](../../htmlcanvaselement/width) and [`height`](../../htmlcanvaselement/height) properties of the canvas to the values of the [`clientWidth`](../../element/clientwidth) and [`clientHeight`](../../element/clientheight) properties, respectively.

In contrast, no such assignment is done for the second canvas. The internal [`width`](../../htmlcanvaselement/width) and [`height`](../../htmlcanvaselement/height) properties of the canvas remain at default values, which are different than the actual size of the canvas [`Element`](../../element) in the browser window.

The effect is clearly visible when using [`scissor()`](../../webglrenderingcontext/scissor) and [`clear()`](../../webglrenderingcontext/clear) to draw a square in the center of the canvas, by specifying its position and size in pixels. In the first canvas, we get the desired result. In the second, the square has the wrong shape, size, and position.

    <p>Compare the two canvases.</p>
    <canvas>Your browser does not seem to support
        HTML5 canvas.</canvas>
    <canvas>Your browser does not seem to support
        HTML5 canvas.</canvas>

    body {
      text-align : center;
    }
    canvas {
      display : inline-block;
      width : 120px;
      height : 80px;
      margin : auto;
      padding : 0;
      border : none;
      background-color : black;
    }

    window.addEventListener("load", function() {
      "use strict"
      var firstCanvas = document.getElementsByTagName("canvas")[0],
        secondCanvas = document.getElementsByTagName("canvas")[1];
      firstCanvas.width = firstCanvas.clientWidth;
      firstCanvas.height = firstCanvas.clientHeight;
      [firstCanvas, secondCanvas].forEach(function(canvas) {
        var gl = canvas.getContext("webgl")
          || canvas.getContext("experimental-webgl");
        if (!gl) {
          document.querySelector("p").innerHTML =
            "Failed to get WebGL context. "
            + "Your browser or device may not support WebGL.";
          return;
        }
        gl.viewport(0, 0,
          gl.drawingBufferWidth, gl.drawingBufferHeight);
        gl.enable(gl.SCISSOR_TEST);
        gl.scissor(30, 10, 60, 60);
        gl.clearColor(1.0, 1.0, 0.0, 1.0);
        gl.clear(gl.COLOR_BUFFER_BIT);
      });
    }, false);

The source code of this example is also available on [GitHub](https://github.com/idofilin/webgl-by-example/tree/master/canvas-size-and-webgl).

-   <a href="basic_scissoring" class="button minimal">« Previous</a>
-   <a href="boilerplate_1" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Canvas_size_and_WebGL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Canvas_size_and_WebGL</a>
