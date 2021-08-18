Using shaders to apply color in WebGL
=====================================

-   <a href="adding_2d_content_to_a_webgl_context" class="button minimal">« Previous</a>
-   <a href="animating_objects_with_webgl" class="button minimal">Next »</a>

Having created a square plane in the [previous demonstration](adding_2d_content_to_a_webgl_context), the next obvious step is to add a splash of color to it. We can do this by revising the shaders.

This example uses the glMatrix library to perform its matrix and vertex math. You'll need to include it if you create your own project based on this code. Our sample loads a copy from a CDN in our HTML's [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head).

Applying color to the vertices
------------------------------

In WebGL objects are built using sets of vertices, each of which has a position and a color. By default, all other pixels' colors (and all its other attributes, including position) are computed using interpolation, automatically creating smooth gradients. Previously, our vertex shader didn't apply any specific colors to the vertices. Between this and the fragment shader assigning the fixed color of white to each pixel, the entire square was rendered as solid white.

Let's say we want to render a gradient in which each corner of the square is a different color: red, blue, green, and white. The first thing to do is to establish these colors for the four vertices. To do this, we first need to create an array of vertex colors, then store it into a WebGL buffer. We'll do that by adding the following code to our `initBuffers()` function:

    function initBuffers(){
      ...
      const colors = [
        1.0,  1.0,  1.0,  1.0,    // white
        1.0,  0.0,  0.0,  1.0,    // red
        0.0,  1.0,  0.0,  1.0,    // green
        0.0,  0.0,  1.0,  1.0,    // blue
      ];

      const colorBuffer = gl.createBuffer();
      gl.bindBuffer(gl.ARRAY_BUFFER, colorBuffer);
      gl.bufferData(gl.ARRAY_BUFFER, new Float32Array(colors), gl.STATIC_DRAW);

      return {
        position: positionBuffer,
        color: colorBuffer,
      };
    }

This code starts by creating a JavaScript array containing four 4-value vectors, one for each vertex color. Then a new WebGL buffer is allocated to store these colors, and the array is converted into floats and stored into the buffer.

To use these colors, the vertex shader needs to be updated to pull the appropriate color from the color buffer:

      const vsSource = `
        attribute vec4 aVertexPosition;
        attribute vec4 aVertexColor;

        uniform mat4 uModelViewMatrix;
        uniform mat4 uProjectionMatrix;

        varying lowp vec4 vColor;

        void main(void) {
          gl_Position = uProjectionMatrix * uModelViewMatrix * aVertexPosition;
          vColor = aVertexColor;
        }
      `;

The key difference here is that for each vertex, we pass its color using a `varying` to the fragment shader.

Coloring the fragments
----------------------

As a refresher, here's what our fragment shader looked like previously:

      const fsSource = `
        void main() {
          gl_FragColor = vec4(1.0, 1.0, 1.0, 1.0);
        }
      `;

In order to pick up the interpolated color for each pixel, we need to change this to fetch the value from the `vColor` varying:

      const fsSource = `
        varying lowp vec4 vColor;

        void main(void) {
          gl_FragColor = vColor;
        }
      `;

Each fragment receives the interpolated color based on its position relative to the vertex positions instead of a fixed value.

Drawing using the colors
------------------------

Next, it's necessary to add code to look up the attribute location for the colors and setup that attribute for the shader program:

      const programInfo = {
        program: shaderProgram,
        attribLocations: {
          vertexPosition: gl.getAttribLocation(shaderProgram, 'aVertexPosition'),
          vertexColor: gl.getAttribLocation(shaderProgram, 'aVertexColor'),
        },
        ...

Then, `drawScene()` can have the following added to it so it actually uses these colors when drawing the square:

      // Tell WebGL how to pull out the colors from the color buffer
      // into the vertexColor attribute.
      {
        const numComponents = 4;
        const type = gl.FLOAT;
        const normalize = false;
        const stride = 0;
        const offset = 0;
        gl.bindBuffer(gl.ARRAY_BUFFER, buffers.color);
        gl.vertexAttribPointer(
            programInfo.attribLocations.vertexColor,
            numComponents,
            type,
            normalize,
            stride,
            offset);
        gl.enableVertexAttribArray(
            programInfo.attribLocations.vertexColor);
      }

[View the complete code](https://github.com/mdn/webgl-examples/tree/gh-pages/tutorial/sample3) | [Open this demo on a new page](https://mdn.github.io/webgl-examples/tutorial/sample3/)

-   <a href="adding_2d_content_to_a_webgl_context" class="button minimal">« Previous</a>
-   <a href="animating_objects_with_webgl" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Using_shaders_to_apply_color_in_WebGL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Using_shaders_to_apply_color_in_WebGL</a>
