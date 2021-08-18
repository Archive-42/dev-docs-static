Boilerplate 1
=============

### Boilerplate code for setting up WebGL rendering context

-   <a href="canvas_size_and_webgl" class="button minimal">« Previous</a>
-   <a href="scissor_animation" class="button minimal">Next »</a>

This example describes repeated pieces of code that will be hidden from now on, as well as defining a JavaScript utility function to make WebGL initialization easier.

By now you are quite used to seeing the same pieces of [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML), [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS), and [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/JavaScript) repeated again and again. So we are going to hide them from now on. This would allow us to focus on the interesting pieces of code that are most relevant for learning [WebGL](https://developer.mozilla.org/en-US/docs/Glossary/WebGL).

Specifically, the HTML has a [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) element that contains some descriptive text about the page and may also hold error messages; a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element; and optionally a [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button). The CSS contains rules for `body`, `canvas`, and `button`. Any additional non-trivial CSS and HTML will be displayed on the pages of specific examples.

In following examples, we will use a JavaScript helper function, `getRenderingContext()`, to initialize the [WebGL rendering context](../../webglrenderingcontext). By now, you should be able to understand what the function does. Basically, it gets the WebGL rendering context from the canvas element, initializes the drawing buffer, clears it black, and returns the initialized context. In case of error, it displays an error message and returns [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null).

Finally, all JavaScript code will run within an immediate function, which is a common JavaScript technique (see [Function](https://developer.mozilla.org/en-US/docs/Glossary/Function)). The function declaration and invocation will also be hidden.

### HTML

    <p>[ Some descriptive text about the example. ]</p>
    <button>[ Optional button element. ]</button>
    <canvas>Your browser does not seem to support
        HTML5 canvas.</canvas>

### CSS

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
      display : block;
      font-size : inherit;
      margin : auto;
      padding : 0.6em;
    }

### JavaScript

    function getRenderingContext() {
      var canvas = document.querySelector("canvas");
      canvas.width = canvas.clientWidth;
      canvas.height = canvas.clientHeight;
      var gl = canvas.getContext("webgl")
        || canvas.getContext("experimental-webgl");
      if (!gl) {
        var paragraph = document.querySelector("p");
        paragraph.innerHTML = "Failed to get WebGL context."
          + "Your browser or device may not support WebGL.";
        return null;
      }
      gl.viewport(0, 0,
        gl.drawingBufferWidth, gl.drawingBufferHeight);
      gl.clearColor(0.0, 0.0, 0.0, 1.0);
      gl.clear(gl.COLOR_BUFFER_BIT);
      return gl;
    }

The source code of this example is also available on [GitHub](https://github.com/idofilin/webgl-by-example/tree/master/boilerplate-1).

-   <a href="canvas_size_and_webgl" class="button minimal">« Previous</a>
-   <a href="scissor_animation" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Boilerplate_1" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Boilerplate_1</a>
