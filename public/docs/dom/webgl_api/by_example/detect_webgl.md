Detect WebGL
============

### Feature-detecting WebGL

-   <a href="../by_example" class="button minimal">« Previous</a>
-   <a href="clearing_with_colors" class="button minimal">Next »</a>

This example demonstrates how to detect a [WebGL](https://developer.mozilla.org/en-US/docs/Glossary/WebGL) rendering context and reports the result to the user.

In this first example we are going to check whether the browser supports [WebGL](https://developer.mozilla.org/en-US/docs/Glossary/WebGL). To that end we will try to obtain the [WebGL rendering context](../../webglrenderingcontext) from a [`canvas`](../../htmlcanvaselement) element. The [WebGL rendering context](../../webglrenderingcontext) is an interface, through which you can set and query the state of the graphics machine, send data to the WebGL, and execute draw commands.

Saving the state of the graphics machine within a single context interface is not unique to [WebGL](https://developer.mozilla.org/en-US/docs/Glossary/WebGL). This is also done in other graphics [API](https://developer.mozilla.org/en-US/docs/Glossary/API), such as the [canvas 2D rendering context](../../canvasrenderingcontext2d). However, the properties and variables you can tweak are different for each [API](https://developer.mozilla.org/en-US/docs/Glossary/API).

    <p>[ Here would go the result of WebGL feature detection ]</p>
    <button>Press here to detect WebGLRenderingContext</button>

    body {
      text-align : center;
    }
    button {
      display : block;
      font-size : inherit;
      margin : auto;
      padding : 0.6em;
    }

    // Run everything inside window load event handler, to make sure
    // DOM is fully loaded and styled before trying to manipulate it.
    window.addEventListener("load", function() {
      var paragraph = document.querySelector("p"),
        button = document.querySelector("button");
      // Adding click event handler to button.
      button.addEventListener("click", detectWebGLContext, false);
      function detectWebGLContext () {
        // Create canvas element. The canvas is not added to the
        // document itself, so it is never displayed in the
        // browser window.
        var canvas = document.createElement("canvas");
        // Get WebGLRenderingContext from canvas element.
        var gl = canvas.getContext("webgl")
          || canvas.getContext("experimental-webgl");
        // Report the result.
        if (gl && gl instanceof WebGLRenderingContext) {
          paragraph.textContent =
            "Congratulations! Your browser supports WebGL.";
        } else {
          paragraph.textContent = "Failed to get WebGL context. "
            + "Your browser or device may not support WebGL.";
        }
      }
    }, false);

The source code of this example is also available on [GitHub](https://github.com/idofilin/webgl-by-example/tree/master/detect-webgl).

-   <a href="../by_example" class="button minimal">« Previous</a>
-   <a href="clearing_with_colors" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Detect_WebGL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Detect_WebGL</a>
