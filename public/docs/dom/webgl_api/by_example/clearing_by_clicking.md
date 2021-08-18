Clearing by clicking
====================

### Clearing the rendering context with random colors

-   <a href="clearing_with_colors" class="button minimal">« Previous</a>
-   <a href="simple_color_animation" class="button minimal">Next »</a>

This example demonstrates how to combine user interaction with WebGL graphics operations by clearing the rendering context with a random color when the user clicks.

This example provides a simple illustration of how to combine [WebGL](https://developer.mozilla.org/en-US/docs/Glossary/WebGL) and user interaction. Every time the user clicks the canvas or the button, the canvas is cleared with a new randomly chosen color.

Note how we embed the [WebGL](https://developer.mozilla.org/en-US/docs/Glossary/WebGL) function calls inside the event handler function.

    <p>A very simple WebGL program that still shows some color and
        user interaction.</p>
    <p>You can repeatedly click the empty canvas or the button below
        to change color.</p>
    <canvas id="canvas-view">Your browser does not seem to support
        HTML5 canvas.</canvas>
    <button id="color-switcher">Press here to switch color</button>

    body {
      text-align : center;
    }
    canvas {
      display : block;
      width : 280px;
      height : 210px;
      margin : auto;
      padding : 0;
      border : none;
      background-color : black;
    }
    button {
      display : inline-block;
      font-size : inherit;
      margin : auto;
      padding : 0.6em;
    }

    window.addEventListener("load", function setupWebGL (evt) {
      "use strict"

      // Cleaning after ourselves. The event handler removes
      // itself, because it only needs to run once.
      window.removeEventListener(evt.type, setupWebGL, false);

      // Adding the same click event handler to both canvas and
      // button.
      var canvas = document.querySelector("#canvas-view");
      var button = document.querySelector("#color-switcher");
      canvas.addEventListener("click", switchColor, false);
      button.addEventListener("click", switchColor, false);

      // A variable to hold the WebGLRenderingContext.
      var gl;

      // The click event handler.
      function switchColor () {
        // Referring to the externally defined gl variable.
        // If undefined, try to obtain the WebGLRenderingContext.
        // If failed, alert user of failure.
        // Otherwise, initialize the drawing buffer (the viewport).
        if (!gl) {
          gl = canvas.getContext("webgl")
            || canvas.getContext("experimental-webgl");
          if (!gl) {
            alert("Failed to get WebGL context.\n"
              + "Your browser or device may not support WebGL.");
            return;
          }
          gl.viewport(0, 0,
            gl.drawingBufferWidth, gl.drawingBufferHeight);
        }
        // Get a random color value using a helper function.
        var color = getRandomColor();
        // Set the clear color to the random color.
        gl.clearColor(color[0], color[1], color[2], 1.0);
        // Clear the context with the newly set color. This is
        // the function call that actually does the drawing.
        gl.clear(gl.COLOR_BUFFER_BIT);
      }

      // Random color helper function.
      function getRandomColor() {
        return [Math.random(), Math.random(), Math.random()];
      }

    }, false);

The source code of this example is also available on [GitHub](https://github.com/idofilin/webgl-by-example/tree/master/clearing-by-clicking).

-   <a href="clearing_with_colors" class="button minimal">« Previous</a>
-   <a href="simple_color_animation" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Clearing_by_clicking" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Clearing_by_clicking</a>