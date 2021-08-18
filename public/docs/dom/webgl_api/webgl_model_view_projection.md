WebGL model view projection
===========================

This article explores how to take data within a [WebGL](../webgl_api) project, and project it into the proper spaces to display it on the screen. It assumes a knowledge of basic matrix math using translation, scale, and rotation matrices. It explains the three core matrices that are typically used when composing a 3D scene: the model, view and projection matrices.

**Note**: This article is also available as an [MDN content kit](https://github.com/TatumCreative/mdn-model-view-projection). It also uses a collection of [utility functions](https://github.com/TatumCreative/mdn-webgl) available under the `MDN` global object.

The model, view, and projection matrices
----------------------------------------

Individual transformations of points and polygons in space in WebGL are handled by the basic transformation matrices like translation, scale, and rotation. These matrices can be composed together and grouped in special ways to make them useful for rendering complicated 3D scenes. These composed matrices ultimately move the original model data around into a special coordinate space called **clip space**. This is a 2 unit wide cube, centered at (0,0,0), and with corners that range from (-1,-1,-1) to (1,1,1). This clip space is compressed down into a 2D space and rasterized into an image.

The first matrix discussed below is the **model matrix**, which defines how you take your original model data and move it around in 3D world space. The **projection matrix** is used to convert world space coordinates into clip space coordinates. A commonly used projection matrix, the **perspective projection matrix**, is used to mimic the *effects* of a typical camera serving as the stand-in for the viewer in the 3D virtual world. The **view matrix** is responsible for moving the objects in the scene to simulate the position of the camera being changed, altering what the viewer is currently able to see.

The sections below offer an in-depth look into the ideas behind and implementation of the model, view, and projection matrices. These matrices are core to moving data around on the screen, and are concepts that transcend individual frameworks and engines.

Clip space
----------

In a WebGL program, data is typically uploaded to the GPU with its own coordinate system and then the vertex shader transforms those points into a special coordinate system known as **clip space**. Any data which extends outside of the clip space is clipped off and not rendered. However, if a triangle straddles the border of this space then it is chopped up into new triangles, and only the parts of the new triangles that are in clip space are kept.

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB2aWV3Qm94PSIwIDAgNTAwIDQzMiI+PHBhdGggZmlsbD0iI0Y0RjRGNCIgZD0iTTExOS45IDEyOC4zbDE0LjggMjIwLjMgMjIyLjUgOS4yIDYwLjUtMTEyLTQuNS0xOTAuOUgyMjAuOXoiLz48cGF0aCBmaWxsPSIjMDBDRTAwIiBkPSJNMjgwLjcgMTAzLjNsLTYuNS01LjUtNi41IDUuNSA2LjUtMTQuMXoiLz48cGF0aCBmaWxsPSIjQTUwMDAwIiBkPSJNMzcxLjggMjAxLjZsNS40LTYuNS01LjQtNi42IDE0LjEgNi42eiIvPjxwYXRoIGZpbGw9IiMwQTAwRUMiIGQ9Ik0zMTIuNyAxNjUuOGwtNS42LTIuOC05LjMgMiAxMi43LTYuNHoiLz48cGF0aCBmaWxsPSJub25lIiBzdHJva2U9IiMwQTAwRUMiIHN0cm9rZS13aWR0aD0iNCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiIGQ9Ik0yNzguNyAxOTMuNWwyOC4xLTMwLjgiLz48cGF0aCBmaWxsPSJub25lIiBzdHJva2U9IiMwMENFMDAiIHN0cm9rZS13aWR0aD0iNCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiIGQ9Ik0yNzguOCAxOTMuNWwtNC42LTk1LjgiLz48cGF0aCBmaWxsPSJub25lIiBzdHJva2U9IiNBNTAwMDAiIHN0cm9rZS13aWR0aD0iNCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiIGQ9Ik0yNzguNyAxOTMuNWw5OS44IDEuNyIvPjxnIGZvbnQtZmFtaWx5PSInQ291cmllck5ld1BTTVQnIiBmb250LXNpemU9IjEwIj48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgyNTguNjk2IDIwNS4zOTMpIj4oMCwwLDApPC90ZXh0Pjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDM5Ni44NjMgNDguNTYpIj4oMSwxLDEpPC90ZXh0Pjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDEwMi44NiAzNjQuMDYpIj4oLTEsLTEsLTEpPC90ZXh0Pjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDMyOS4xOTQgMzcwLjA2KSI+KDEsLTEsLTEpPC90ZXh0Pjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDQxNy4xOTUgMjU3LjA2KSI+KDEsLTEsMSk8L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMjI5LjE5NCAyNTUuMDYpIj4oLTEsLTEsMSk8L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTkzLjUyOSA0OC43MjcpIj4oLTEsMSwxKTwvdGV4dD48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MC41MjggMTMwLjA2KSI+KC0xLDEsLTEpPC90ZXh0Pjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDM1NS4xOTUgMTM5LjA2KSI+KDEsMSwtMSk8L3RleHQ+PC9nPjxnIG9wYWNpdHk9Ii4yIiBmaWxsPSJub25lIiBzdHJva2U9IiM2RDZENkQiIHN0cm9rZS13aWR0aD0iLjc1IiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiPjxwYXRoIGQ9Ik0xODkgMjg3bDIwMCA2LTUuMy0yMDMuM0wxNzUgODh6Ii8+PHBhdGggZD0iTTI0NCAzNTEuNWwtMTAuNS0yMjIgNzQtNzRMMzEzIDI0M3oiLz48cGF0aCBkPSJNMTI3LjUgMjM1LjZsMjI0LjUgMi45IDYzLTc5LTE4OC43LTEuOHptMTEwLjUuOWw3Mi41LTc4TTE4MiAxOTJsMjA0IDNtLTEwMi43IDk0LjhsLTkuMy0yMDEiLz48L2c+PGRlZnM+PHBhdGggaWQ9ImEiIGQ9Ik00MTMuMiA1NC45bDQuNSAxOTAuOS0xODcuMy00LjUtOS41LTE4Ni40eiIvPjwvZGVmcz48Y2xpcFBhdGggaWQ9ImIiPjx1c2UgeGxpbms6aHJlZj0iI2EiIG92ZXJmbG93PSJ2aXNpYmxlIi8+PC9jbGlwUGF0aD48cGF0aCBjbGlwLXBhdGg9InVybCgjYikiIGZpbGw9Im5vbmUiIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLXdpZHRoPSIzIiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiIGQ9Ik00MTMuMiA1NC45bDQuNSAxOTAuOS0xODcuMy00LjUtOS41LTE4Ni40eiIvPjxkZWZzPjxwYXRoIGlkPSJjIiBkPSJNMzQ5LjcgMTMwLjVsNy41IDIyNy4zLTIyMi44LTguNS0xNC41LTIyMXoiLz48L2RlZnM+PGNsaXBQYXRoIGlkPSJkIj48dXNlIHhsaW5rOmhyZWY9IiNjIiBvdmVyZmxvdz0idmlzaWJsZSIvPjwvY2xpcFBhdGg+PHBhdGggY2xpcC1wYXRoPSJ1cmwoI2QpIiBmaWxsPSJub25lIiBzdHJva2U9IiMwMDAiIHN0cm9rZS13aWR0aD0iMyIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBkPSJNMzQ5LjcgMTMwLjVsNy41IDIyNy4zLTIyMi44LTguNS0xNC41LTIyMXoiLz48ZGVmcz48cGF0aCBpZD0iZSIgZD0iTTM0OS43IDEzMC41bDYzLjUtNzUuNiA0LjUgMTkwLjktNjAuNSAxMTJ6Ii8+PC9kZWZzPjxjbGlwUGF0aCBpZD0iZiI+PHVzZSB4bGluazpocmVmPSIjZSIgb3ZlcmZsb3c9InZpc2libGUiLz48L2NsaXBQYXRoPjxwYXRoIGNsaXAtcGF0aD0idXJsKCNmKSIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjMDAwIiBzdHJva2Utd2lkdGg9IjMiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgZD0iTTM0OS43IDEzMC41bDYzLjUtNzUuNiA0LjUgMTkwLjktNjAuNSAxMTJ6Ii8+PGRlZnM+PHBhdGggaWQ9ImciIGQ9Ik0zNTcuMiAzNTcuOGwtMjIyLjgtOC41IDk2LTEwOCAxODcuMyA0LjV6Ii8+PC9kZWZzPjxjbGlwUGF0aCBpZD0iaCI+PHVzZSB4bGluazpocmVmPSIjZyIgb3ZlcmZsb3c9InZpc2libGUiLz48L2NsaXBQYXRoPjxwYXRoIGNsaXAtcGF0aD0idXJsKCNoKSIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjMDAwIiBzdHJva2Utd2lkdGg9IjMiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgZD0iTTM1Ny4yIDM1Ny44bC0yMjIuOC04LjUgOTYtMTA4IDE4Ny4zIDQuNXoiLz48ZGVmcz48cGF0aCBpZD0iaSIgZD0iTTEzNC40IDM0OS4zbC0xNC41LTIyMSAxMDEtNzMuNCA5LjUgMTg2LjR6Ii8+PC9kZWZzPjxjbGlwUGF0aCBpZD0iaiI+PHVzZSB4bGluazpocmVmPSIjaSIgb3ZlcmZsb3c9InZpc2libGUiLz48L2NsaXBQYXRoPjxwYXRoIGNsaXAtcGF0aD0idXJsKCNqKSIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjMDAwIiBzdHJva2Utd2lkdGg9IjMiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgZD0iTTEzNC40IDM0OS4zbC0xNC41LTIyMSAxMDEtNzMuNCA5LjUgMTg2LjR6Ii8+PGRlZnM+PHBhdGggaWQ9ImsiIGQ9Ik0xMTkuOSAxMjguM2wxMDEtNzMuNGgxOTIuM2wtNjMuNSA3NS42eiIvPjwvZGVmcz48Y2xpcFBhdGggaWQ9ImwiPjx1c2UgeGxpbms6aHJlZj0iI2siIG92ZXJmbG93PSJ2aXNpYmxlIi8+PC9jbGlwUGF0aD48cGF0aCBjbGlwLXBhdGg9InVybCgjbCkiIGZpbGw9Im5vbmUiIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLXdpZHRoPSIzIiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiIGQ9Ik0xMTkuOSAxMjguM2wxMDEtNzMuNGgxOTIuM2wtNjMuNSA3NS42eiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDE0IDQxOC4zMzQpIiBmb250LWZhbWlseT0iJ0NvdXJpZXJOZXdQU01UJyIgZm9udC1zaXplPSIxOS42MzMiPkNsaXBzcGFjZTwvdGV4dD48L3N2Zz4=" alt="A 3d graph showing clip space in WebGL." width="500" height="432" />

The above graphic is a visualization of the clip space that all of the points must fit into. It is a cube two units on each side, with one corner at (-1,-1,-1) and the opposite corner at (1,1,1). The center of the cube is the point (0,0,0). This 8 cubic meter coordinate system used by clip space is known as normalized device coordinates (NDC). You may encouter that term from time to time while researching and working with WebGL code.

For this section we will put our data into the clip space coordinate system directly. Normally model data is used that is in some arbitrary coordinate system, and is then transformed using a matrix, converting the model coordinates into the clip space coordinate system. For this example, it's easiest to illustrate how clip space works by using model coordinate values ranging from (-1,-1,-1) to (1,1,1). The code below will create 2 triangles that will draw a square on the screen. The Z depth in the squares determines what gets drawn on top when the squares share the same space. The smaller Z values are rendered on top of the larger Z values.

### WebGLBox example

This example will create a custom `WebGLBox` object that will draw a 2D box on the screen.

**Note**: The code for each WebGLBox example is available in this [github repo](https://github.com/TatumCreative/mdn-model-view-projection/tree/master/lessons) and is organized by section. In addition there is a JSFiddle link at the bottom of each section.

#### WebGLBox constructor

The constructor looks like this:

    function WebGLBox() {
      // Setup the canvas and WebGL context
      this.canvas = document.getElementById('canvas');
      this.canvas.width = window.innerWidth;
      this.canvas.height = window.innerHeight;
      this.gl = MDN.createContext(canvas);

      var gl = this.gl;

      // Setup a WebGL program, anything part of the MDN object is defined outside of this article
      this.webglProgram = MDN.createWebGLProgramFromIds(gl, 'vertex-shader', 'fragment-shader');
      gl.useProgram(this.webglProgram);

      // Save the attribute and uniform locations
      this.positionLocation = gl.getAttribLocation(this.webglProgram, 'position');
      this.colorLocation = gl.getUniformLocation(this.webglProgram, 'color');

      // Tell WebGL to test the depth when drawing, so if a square is behind
      // another square it won't be drawn
      gl.enable(gl.DEPTH_TEST);

    }

#### WebGLBox draw

Now we'll create a method to draw a box on the screen.

    WebGLBox.prototype.draw = function(settings) {
      // Create some attribute data; these are the triangles that will end being
      // drawn to the screen. There are two that form a square.

      var data = new Float32Array([

        //Triangle 1
        settings.left,  settings.bottom, settings.depth,
        settings.right, settings.bottom, settings.depth,
        settings.left,  settings.top,    settings.depth,

        //Triangle 2
        settings.left,  settings.top,    settings.depth,
        settings.right, settings.bottom, settings.depth,
        settings.right, settings.top,    settings.depth
      ]);

      // Use WebGL to draw this onto the screen.

      // Performance Note: Creating a new array buffer for every draw call is slow.
      // This function is for illustration purposes only.

      var gl = this.gl;

      // Create a buffer and bind the data
      var buffer = gl.createBuffer();
      gl.bindBuffer(gl.ARRAY_BUFFER, buffer);
      gl.bufferData(gl.ARRAY_BUFFER, data, gl.STATIC_DRAW);

      // Setup the pointer to our attribute data (the triangles)
      gl.enableVertexAttribArray(this.positionLocation);
      gl.vertexAttribPointer(this.positionLocation, 3, gl.FLOAT, false, 0, 0);

      // Setup the color uniform that will be shared across all triangles
      gl.uniform4fv(this.colorLocation, settings.color);

      // Draw the triangles to the screen
      gl.drawArrays(gl.TRIANGLES, 0, 6);
    }

The shaders are the bits of code written in GLSL that take our data points and ultimately render them to the screen. For convenience, these shaders are stored in a [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element that is brought into the program through the custom function `MDN.createWebGLProgramFromIds()`. This function is part of a collection of [utility functions](https://github.com/TatumCreative/mdn-webgl) written for these tutorials and is not explained in depth here. This function handles the basics of taking some GLSL source code and compiling it into a WebGL program. The function takes three parameters — the context to render the program in, the ID of the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element containing the vertex shader, and the ID of the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element containing the fragment shader. The vertex shader positions the vertices, and the fragment shader colors each pixel.

First take a look at the vertex shader that will move the vertices on the screen:

    // The individual position vertex
    attribute vec3 position;

    void main() {
      // the gl_Position is the final position in clip space after the vertex shader modifies it
      gl_Position = vec4(position, 1.0);
    }

Next, to actually rasterize the data into pixels, the fragment shader evaluates everything on a per pixel basis, setting a single color. The GPU calls the shader function for each pixel it needs to render; the shader's job is to return the color to use for that pixel.

    precision mediump float;
    uniform vec4 color;

    void main() {
      gl_FragColor = color;
    }

With those settings included, it's time to directly draw to the screen using clip space coordinates.

    var box = new WebGLBox();

First draw a red box in the middle.

    box.draw({
      top    : 0.5,             // x
      bottom : -0.5,            // x
      left   : -0.5,            // y
      right  : 0.5,             // y

      depth  : 0,               // z
      color  : [1, 0.4, 0.4, 1] // red
    });

Next, draw a green box up top and behind the red box.

    box.draw({
      top    : 0.9,             // x
      bottom : 0,               // x
      left   : -0.9,            // y
      right  : 0.9,             // y

      depth  : 0.5,             // z
      color  : [0.4, 1, 0.4, 1] // green
    });

Finally, for demonstration that clipping is actually going on, this box doesn't get drawn because it's entirely outside of clip space. The depth is outside of the -1.0 to 1.0 range.

    box.draw({
      top    : 1,               // x
      bottom : -1,              // x
      left   : -1,              // y
      right  : 1,               // y

      depth  : -1.5,            // z
      color  : [0.4, 0.4, 1, 1] // blue
    });

#### The results

[View on JSFiddle](https://jsfiddle.net/mff99yu5)

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAyAAAAISCAMAAAADa1tIAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAEOUExURV7/XP9mY1v/Wf9oZff39/9ta+rq6v////9lYk7/TLH/sP9WU/9XY3D/bl3/XPD/8P9kYcxPTY03Nv9hYmX/ZP+Mi6i+YUv/XHMsK/9qaHCNcNfJ11f/VW7/bLFEQ/92dLCwsP/x8fpiX1P/XG70XfF2Yvj5+GL/YCpyKHJyclv5WWptavFeW0CwP4uOjpaVlsrKytxWVKQ/Pt3c3cRLSu/v75E4N4k0M9TV1U3cTTujOmguKNVpZ/z8/IaGhrm5ueXl5S6ZLGiYRFfvVGrwX6YmOb1JRzGHMMLCwjOwOKWipSZlJXp6erM3QOpyX0G3QIitiFdXV9bI1tlFTN3q3W2KaZOpVUVHPj3/OY6JS4TcfIsAABD+SURBVHja7N0PW9PWAsBhYingVVgjbCN3ih1sFKWsxLbSqkg3drEiuwy5j9u+/xe5KX8Gtk6Ps0ibvT+BR/C0kHBeklA8THSmNDJt7x+trz/48NPRzrad9VnqTExOa3QqP+hMNpvNqfc+ZS9W7arP0yQgIwbE1AdEVwFku9U5+9vqZsueBASQS5/GzMZkuXv22ma3SwgggFwcPDrdye3p5rmKzdWpTbsSEEDOm9opbzanp/4Est10BAEEkEtCekeMTk9FvT493Z2qO4IAkoNOvtCXa5vT3drOJwFZza5Bmjvl7O7K+5mUnW7TzgVk/Gs9yPZ++bfa9POjTwNygmRy9fxz2eQDkFwAOejt/fJB62Bn+pOBCJB81a3VDmq17JqhdlSbBgQQ9QP5IQOSXTe01juAAKK/OMWarh9MAQKIBtpcP7kGWV9fdw0CiAY6fTyvVe6WW4AAooG2+98ACCB6T4AAIkAAESCACBBABAggAkSAACJAABEgeW3nAJDxBLL6L32Gfl3/dTC75QpaHTKQLyq/39RVd/fl2o8DvWjftWeG3O+VL4YN5N7NG7rqKhtrlYVKXxN379ozQ+7mvaEDmb05oatuYWPtYcVuuPpuzgICiAABRIAAIkAECCACBBABAogAAQQQQAABBBBAAAFEgAAiQAARIIAIEAECiAABRIAAIkAAAQQQQAABBBBAABEggAiQfxCQgWV/iAFEF0AmHvY3Z8cAojMgLwZaay/YM4DoFEh7t93fnJMsQHQGpLIwUMU5FiA6vwbpHS4ql54EiPqACBABAogAAUSAAAIIIIAAAggggAACCCCACBBABAggAkSAACJAABEggAgQQAABBBBAAAEEEEAECCACBBABAogAESCA6OOAVO5Z9gcQ/SWQjcONw8PLzxsbuw4qgOgMyI9P+v+8sPQoIPrzFMvKioDogxfpl18KEPUBESACBBABAogAAQQQQAABBBBAAAEEEEAAESCACBBABIgAAUSAACJAABEggAACCCCAAAIIIIAIEEAECCACBBABIkAA0UcBWaj0Z78AoosjyNxAdgwgOgPyYqA1KysConMg7cFclgCicyCWHgVE770GsRsAESCACBBABAgggAACCCCAAAIIIAIEEAECiAABRIAIEEAECCACBBABAggggAACCCCAAAKIAAFEgAAiQAD5O81dLKBlKS1AAHmrSubjYfvspnO77Yf2JSB9X0Dz0F8sHPehJm7sTlQeHh62T25baR9mQK57UwAZMR9f56GVw7WFoFbevtlue26l3V5pn77Wbn+9cu2bMgfIKHWj8lUu+um3n4J689at3mRv+erNm97Tyat//PHm2rekcgOQEWrlu+XbOWj+l8X/BHU8/9btjhu3bh8fJ8e3Tu/l/vLxdW/J8ncrgIwUkO9vz49/ydJiUkwCit66WbScJkm10YgLydKjJIrjRppc74bc/h6QkQMyM/4VlxaXC3/jdlH2XKjGy1FUTaNoOU4L17sdJUAAGSUgPSGlQjEqlZKkVIqS5Lo3BBBARgrIqAUIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAAALIlQBJooEAAQQQRxBAAHl/UbK0uDXQYloEBBBAMiDZESRO+4urESCAAHJ6ipUUi0ny1lOxUAIEEEAurkFOjxiXXwICCCAu0gEBBBBAAAEEEEAAAQQQQAABBBBAAAEEEEAAAQQQQAABBBBAAAEEEEAAAQQQQAABBBBAAAEEEEAAAQQQQAABBBBAAAEEEEAAAQQQQAABBBBA/i6QpDiQZX8AAaRXb+G4vcZeX0vVAiCAAHK69Ojj/u5spQkggAByfoqV9Bc5xQIEkPOL9CQHv/0AEEB8FwsQQAABBBBAAAEE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AggggAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggADyLkD2jP0xWREQQOrqwXFfdjM4DhBAHoEMr6/uzu+q269fRo8CAsjzHmR3uvsHHO8OCCCAAAKIq1iAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAAAIIIB8DyPAEhpoAAsh7ARl+GjYzehQQQOrqyYr/NDu/ux0CAgggT7N5l9PpcvtraTYvIIA8n2Lt1HWKBQggrmIBAggggAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAAALI24A8D9A6/CgtQAA5MiCD7rfN9JPOt5tBBxBAGkAGH79hBaTzurt2BtPr2279Xfd2+uWmc9gHAsjRAemenUAX/+4bPbpb92L7bp8Hg4ufP8+WT3+bLs8uDv1IPgNyZEAuv16eQMurH63afrBfq59c1renH9f/4OCPBBC9Q2E0blOZbN0rzbJJUN2SdP2DfmEpATlJIOXotXddFFnFYh4GFZUks5SAnCSQ768GEkyK6gCSJY9UcksJCCACBBABIkAAESCACBBABAggAkSAACJAABEggAgQQAQIIAJEgAAiQAARIIAIEEAEiAABRIAAIkAAESCACBABAogAAURvARLF47hxm02sCyBaAwnnzcKFdQFETrEAESCACBBABAggAgQQQAARIIAIEEAECCACBBABIkAAESCACBBABAggAkSAACJAABEggAgQQASIAAFEgAAiQAARIIAIEEB0RECySaMsS60LIHoCEs12KjPrAojWR5BekDezLIDIHgQQAQKIAAFEgAAiQAABBBABAogAAUSAACJAABEgAgQQAQKIAAFEgAAiQAQIIAIEEAECiAABRIAIEEAECCACBBABAogAAURHBCSKdxpPrAsgWgMJ52GzhXUBRE6xABEggAgQQAQIIAIEEEAAESCACBBABAggAgQQASJAABEggAgQQAQIIAJEgAAiQAARIIAIEEAEiAABRIAAIkAAESCACBBAdERAJotJM08RIFoDiWY7lZl1AUTrI0gajBr1cusCiOxBABEggAgQQAQIIPojJuIkKOI5IIBoL5CHOJjdAwKIXhBSZuXcKRYg2i5dxas4rL6J72N7kKMF4gk5OJAsWgBypI0AOXyTsg8IIHppDxJFkT0IIHqhLCzCDBBA1OJoAgggAgQQAQKIAAFEHwNInmzeTRkVPoMICCCNemGx/i5JCAEEkF+exX6a5kG6UZGM+omlBASQTf15UYyC/v9A8tQRBBBAGi3qw8akolH0J44ggACyXTqv348PV48HlNRS/i4gZsqcCJB8lG8+utDzGYbfFiDHBeQ+btPYHuMPlf8Hzgr2YFhDLvIAAAAASUVORK5CYII=" alt="The results of drawing to clip space using WebGL." width="800" height="530" />

#### Exercise

A helpful exercise at this point is to move the boxes around the clip space by varying the code to get a feel for how points get clipped and moved around in clip space. Try drawing a picture like a boxy smiley face with a background.

Homogeneous coordinates
-----------------------

The main line of the previous clip space vertex shader contained this code:

    gl_Position = vec4(position, 1.0);

The `position` variable was defined in the `draw()` method and passed in as an attribute to the shader. This is a three dimensional point, but the `gl_Position` variable that ends up getting passed down through the pipeline is actually 4 dimensional — instead of `(x, y, z)` it is `(x, y, z, w)`. There is no letter after `z`, so by convention this fourth dimension is labeled `w`. In the above example the `w` coordinate is set to 1.0.

The obvious question is "why the extra dimension?" It turns out that this addition allows for lots of nice techniques for manipulating 3D data. This added dimension introduces the notion of perspective into the coordinate system; with it in place, we can map 3D coordinates into 2D space—thereby allowing two parallel lines to intersect as they recede into the distance. The value of `w` is used as a divisor for the other components of the coordinate, so that the true values of `x`, `y`, and `z` are computed as `x/w`, `y/w`, and `z/w` (and `w` is then also `w/w`, becoming 1).

A three dimensional point is defined in a typical Cartesian coordinate system. The added fourth dimension changes this point into a [homogeneous coordinate](https://en.wikipedia.org/wiki/Homogeneous_coordinates). It still represents a point in 3D space and it can easily be demonstrated how to construct this type of coordinate through a pair of simple functions.

    function cartesianToHomogeneous(point)
      let x = point[0];
      let y = point[1];
      let z = point[2];

      return [x, y, z, 1];
    }

    function homogeneousToCartesian(point) {
      let x = point[0];
      let y = point[1];
      let z = point[2];
      let w = point[3];

      return [x/w, y/w, z/w];
    }

As previously mentioned and shown in the functions above, the w component divides the x, y, and z components. When the w component is a non-zero real number then homogeneous coordinate easily translates back into a normal point in Cartesian space. Now what happens if the w component is zero? In JavaScript the value returned would be as follows.

    homogeneousToCartesian([10, 4, 5, 0]);

This evaluates to: `[Infinity, Infinity, Infinity]`.

This homogeneous coordinate represents some point at infinity. This is a handy way to represent a ray shooting off from the origin in a specific direction. In addition to a ray, it could also be thought of as a representation of a directional vector. If this homogeneous coordinate is multiplied against a matrix with a translation then the translation is effectively stripped out.

When numbers are extremely large (or extremely small) on computers they begin to become less and less precise because there are only so many ones and zeros that are used to represent them. The more operations that are done on larger numbers, the more and more errors accumulate into the result. When dividing by w, this can effectively increase the precision of very large numbers by operating on two potentially smaller, less error-prone numbers.

The final benefit of using homogeneous coordinates is that they fit very nicely for multiplying against 4x4 matrices. A vertex must match at least one of the dimensions of a matrix in order to be multiplied against it. The 4x4 matrix can be used to encode a variety of useful transformations. In fact, the typical perspective projection matrix uses the division by the w component to achieve its transformation.

The clipping of points and polygons from clip space actually happens after the homogeneous coordinates have been transformed back into Cartesian coordinates (by dividing by w). This final space is known as **normalized device coordinates** or NDC.

To start playing with this idea the previous example can be modified to allow for the use of the `w` component.

    //Redefine the triangles to use the W component
    var data = new Float32Array([
      //Triangle 1
      settings.left,  settings.bottom, settings.depth, settings.w,
      settings.right, settings.bottom, settings.depth, settings.w,
      settings.left,  settings.top,    settings.depth, settings.w,

      //Triangle 2
      settings.left,  settings.top,    settings.depth, settings.w,
      settings.right, settings.bottom, settings.depth, settings.w,
      settings.right, settings.top,    settings.depth, settings.w
    ]);

Then the vertex shader uses the 4 dimensional point passed in.

    attribute vec4 position;

    void main() {
      gl_Position = position;
    }

First, we draw a red box in the middle, but set W to 0.7. As the coordinates get divided by 0.7 they will all be enlarged.

    box.draw({
      top    : 0.5,             // y
      bottom : -0.5,            // y
      left   : -0.5,            // x
      right  : 0.5,             // x
      w      : 0.7,             // w - enlarge this box

      depth  : 0,               // z
      color  : [1, 0.4, 0.4, 1] // red
    });

Now, we draw a green box up top, but shrink it by setting the w component to 1.1

    box.draw({
      top    : 0.9,             // y
      bottom : 0,               // y
      left   : -0.9,            // x
      right  : 0.9,             // x
      w      : 1.1,             // w - shrink this box

      depth  : 0.5,             // z
      color  : [0.4, 1, 0.4, 1] // green
    });

This last box doesn't get drawn because it's outside of clip space. The depth is outside of the -1.0 to 1.0 range.

    box.draw({
      top    : 1,               // y
      bottom : -1,              // y
      left   : -1,              // x
      right  : 1,               // x
      w      : 1.5,             // w - Bring this box into range

      depth  : -1.5,             // z
      color  : [0.4, 0.4, 1, 1] // blue
    });

### The results

[View on JSFiddle](https://jsfiddle.net/mff99yu)

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAyAAAAISCAMAAAADa1tIAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAD/UExURWVg/5xjzF3/W/9fXP9lX/9lVFFg/17/XP////9lYmhj//b29v9hYmpl/+rq61j/XG1p//Ly8vv/+1pW6U//TY3/jDUyhmBb91D/XP/FxP9eYp/GYND/z1b/VC0qdP9YY8ahYv+fnv9YVWJd/EVCs0I/q7CwsD06oP9qaISFhOXl5XNzc/n5+WP/YvDm8FBMzl1Z8Sspb32CfVr+V+5dWZubm6ioqGT2YqA9PG5ubt/f369DQsHBwWtsaj6sPXErKVn0V8vLy9TU1CpzKYUzMmhjYzKJMT85llTnU0xNSiZuJikjXZBi1qNn1T9c/sBkqP3Av4zZX6XBYeuPksunYZMmJQUAABHOSURBVHja7N0LU9pIAMDxqKdgMBhIT5y7HvaOEGgKt0EFK40P8Ki1r5t7fP/Pckt4iAFhe6RI4v/fTkenGW02+2OzYFVzs7Q21Vq9c5V6Tp7BWkmulknT+uS8cTNKkhiq1ZQByJoBYeoDhL4HkFrXHb3V6TKSAAHIxGVsp9M5xx++1/F9hAAEIPe5fiafzo5UdGrZDkMJEICMyvpOJzcBJJ9jBQEIQCaEdEZ/tOXNlp9ts4IAJAEFD/ROs5P2m85SQGpyf57zHfnhnJa84XL8HIMLkPjXOZcT2blrpl/f+UsBCZDkaiMWOXwAJAl1j/uj7xx33/jppYEQQJKV32weN5tyz/BariEAAQjNAiL3Dd1zFyAAoXD57nGwWWgfZwECEJqxSQ/2IL3eBXsQgNBUg5f2uk7wBC1AAEKLAghACCAAIYAAhAACEAIIQAggBBCAEEAAQgABCAEEIAQQegDkvOW0QjVdxgUgNATSnK7NuACEuMUCCAEEIAQQgBBAAEIAAQhAAEIAAQgBBCAEEIAQQABCACGAAIQAAhACCEAIIAAhgBBAAEIAAQgBBCAEEIBQ3IHkafnSznmGkYxkJNcOyMsfafkubxiDSMquH5AXtHSpy48MQiS9XD8gm79s0pLVL29O6gzDsp38srmWQFK0ZBJIqj4V4/KtASS5QK43r8NtMjAAoQGQj++nuvnAGgIQGq4gH64/hLsGCEAoldqsz96D1LnHAggNV5ATlguAEEAAQgABCEAi9QEQgBArCEAIIAABCEAAAhD2IAABCCsIQAACEIAABCAEEPYgBBBWEAIIAQQgBBCAAIQ9CEAAwgoCkO8MhG9L81gBEMZn3gg9ByD7h/RI+5c3DMK88XkGQDY3//r7Z5rd35d3DMKc4flLcQ2JM5D9/VdHP9Hsqu+utvYYhsc6erW//zyA7NGsBkDoseF5NkD2dmlmEkh1RgxM0B5AAHL1bqq3pwgBCA2BvJ0OIAChObdYjAtAaARkq7ob/kUAoQkgBBACCEAAAhCARALkBwrqA2EwRgFk3DYNenfFGIwDyGj92P7z8wbJvtx+2vjCMAR9/nP7B4AMgXz+ukP97CJjMOzrZ4CMgWzsaCQz7WJJZxiCdjYAAhCAAAQgAAEIQAACEIAABCAAAQhAAAIQgAAEIAABCEAAAhCAAAQgBBCAAAQgAAEIQAACEIAABCArBqKZejiAAAQgIyCeVggHEIAAJMiwGwdTFYUJEIDQYAWxPCtciRUEIOAYAtFNIxy3WAABCM9iAQQgAAEIQAACEIAABCAAAQhAAAIQgAAEIAABCEAAAhCAAAQgACGAAAQgAAEIQAACEIAABCAAAQhAAAIQgAAEIAABCEAAAhCAAAQgAAEILQlEH//ndUMHCEAAMolD/vbE8J1SIr4RCkAAEh0QT9MLwhbBGmIIARCAJBWIYar0UJHEYZhCmKI0AGJb3GIBJJlAGmW7vLiKmPxmWbpn20KzLFPIhUTv32sJoQMEIIkEUlHp9gEQuekQnj5YQUoFCcYcb0cAAhBusTStYOmDPYhZrpiSim0ZAAEIm/QHGxGvv/PwPPmHsHRWEIAAZMbrIMFPEzF5HQQgAEl4AAEIQAACEIAABCAAAQhAAAIQgAAEIAABCEAAAhCAAAQgAAEIQAACEAIIQAACEIAABCAAAQhAAAIQgAAEIAABCEAAAhCAAAQgAAEIQAACEIAABCBTQDRTDwcQgABkBMTTCuEAAhCABBl242CqojABAhAarCCWZ4UrsYIABBxDILpphOMWCyAA4VksgAAEIAABCEAAAhCAAAQgAAEIQAACEIAABCAAAQhAAAIQgAAEIAQQgAAEIAABCEAAAhCAAAQgAAEIQAACEIAABCAAAQhAAAIQgAAEIAAhgAAEIAABCEAAAhCAfB8ghjmVDhCAgGMApFG2y6EqlgEQgNAASGWqW4AABCDcYgEEIGzSAQIQgAAEIAABCEAAAhCAAAQgAAEIQAACEIAABCAAAQhACCAAAQhAAAIQgAAEIAABCEAAAhCAAAQgAAEIQAACEIAABCAAAQhAAEIAAQhAAAIQgAAEIAABCEAAsnIgmqmHAwhAADIC4mmFcAABCECCDLtxMFVRmAABCA1WEMuzwpVYQQACjiEQ3TTCcYsFEIDwLBZAAAIQgAAEIAABCEAAAhCAAAQgAAHI/wJSiysQHSBPkh7t0K8DkFq6FgLSdrLDt7pON5ZAhD34kX6GJURBB8jqfHi2GL6kKYSIKZB8Pp12HxgIAck57eEbfs3PxgxI/yU2SxQGF8cUdux8xBaIaVmmLuRD0uBFTTuKh6YnAdJuPzTQad8DaXc67cERwXvd8ZsxAaJ78oHLEJYpvMEKYguLFWQ1WbbtaULzhD5aQUqxBJL1fffegCsNdO+BdH1/AojbSXdjBsQaASlo/S/P0E1PsIKsJs+2LU3ofSD9n8lrmKO1JGZAXMcJGeiGbrEyji/vwpqddN7v+rl43WLpg1ssIXTDtg2tv+KzgqzuFsuQIy9MrSLMgvDs5RfvJ7vFGhroBgay4U2639959PfnrtOO4yZdF7any2ul9xeUEivIiiqVNL3UH3Wt/xyJiOKh6UmA1GpjA+2+ATeduNdBDCNY4yWVGH4ZbLxfBwkGPLjFimLoeaGQFwoTBiTaAAIQgAAEIAABCEAAAhCAAAQgAAEIQAACEIAABCAAAUjigBjmVDpAALLkaPZfOk8EkEbZLoeqWPH7koAIrse6APHbSQBiiUQAMcqNylS3MQQSwfVYCyBtX7trJQCIWfmUiHt3o5KMW6worsdaAGndaRdOAoAY5WJSgCTjPCK4HmsBxLkACEAAAhCAAAQgAAEIQAACEIAABCAAAQhAAAIQgAAEIAABiBqQOkAA8oRA6msOpK4IpFpVBKJHfEFUL5vicXq0H08dyJqfRwTX4yGQqhqQ+lMBcZoZFSD1y/fXdQUg1Xdvt6oKQAxxoPRtkFUviGHfKh2n27cFxePUPq/qeVQSch4RXI9JIHK+nFYVgMj5d1JXAeK/zkULpNnLKQF5/1ENyNurUxUgZuWT0peyql4Q8/aTp/DxdEPtOE0eV1A5Tvk8Kgk5jwiuxwMgwXxRADKcfwuBtO7caIG0ztWAXN5EC6Tc8KK8IEa5UVCcqIqft6H0iKp8HpWEnEcE1+N/AblUBdLLRgokDxCAJAmIEzEQVhCAsIKwggCEFYQVBCAAYQUBCEBYQQACEFYQgACEFQQgAEn8CnLy4uQkJf+BqZO5HR7+e1QNTnjc7vaXHX1m/Qti6oszy0VN7bhGQfHjFaL9eJzHN35eY+fL9u54igTzZffo38PDuZOrPpx/L04WAblQBtJrpXMLSzcv3LmHZfIvz67PzurvP36on80tlXp1tLUrT3j3dEv+Cn7LFaQwM63csLTCwkpapeEpHFeQx6l+vCiP+4bzKCbkPJa/HnIFGc2P4Xw5PXqVSs2dXBJIMP+uz17mM/Pmc6vXVpj2/eO04+PXCikcdRz05nhhvT9kV39MVjx4rMf/Jl5xHt/+qSZnyGC+9BZOrtH8W34+D4/T3KyrUHbxUb8H5X5fVO6f06k2vlqz8zxLqYQcVygXLe8Zne+8475uTM+TfxbOr9HfL5rPOVeprBvZN69W79et+3vL8R7EIJlpF3WTYQiSe5BqaJ5s/bryyZp5CiC/jZ6d2OPHH4SeJeLng0w9i3X/30/3fntuQPj5IABZCGRingAEIAB5HAgrCEAAwgoCEIAABCAAAch/7d1bb9pmHMBhqnaT6whksJQoN7kJmHKQTNBAhVqqjIaqaOnh+3+a2UCyYWCjW5um5PlFibiIcvGGR//3NSdAAAEEEEAA2W6ezYN+vgAEkNMHUt7/F/k8mOfzo4Ekt71gWnwDAsipA+n3GkEwuZ2svo/eYk1n817PFguQ0wcyH5TvIDcZ9weTY7ZYiyzP82HwPecHIIA8GSD9PBkneT84ND+qQIa9cfHVDILs0O8DAsgJAclm4/F4lpUTYfo1V7GyQdabAgLIqQNpFVus8myejPNxcjyQ7HZQkJoAAsjpn0GW/fWJonebHH8VqzcdZr1JExBATh1IY1rczSe9pJX0vuIqlgcKAXkmQDySDggggAACCCCAAAIIIIAAAggggADyn4DUo51CQACBYw3kptPuVOoe9cGygADyLIB0d/oACCCA2GIBAohDOiCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACiAABBBBAAAEEEEAAAQQQQAABBBBAAAEEEEAAAQQQQAABBBBAABEggAACCCCAAAIIIIAAAsijA6lFYTVAAAHkHsiodlENEEAAWVVv35zvdJVGgACi9QSJR3G1axMEEDg2QMKoXs0WCxBAXMUCBBBAAAEEEEAAAQQQQAABBBBAAAEEEEAAAQQQQAABBBBABAgggAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACiAABBBBAAAEEEEAA+T5A6tFOISCAwLEGctNpdyp14zoggGgNpLvTB0AAAcQWCxBAHNIBAQQQQAABBBBAAAEEEEAAAQQQQAABBBBAAAEEEEAECCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAAAKIAAEEEEAAAQQQQAABBBBAHh1ILQqrAQIIIPdARrWLaoAAAsiqevvmfKerNAIEEK0nSDyKq12bIIDAsQESRvVqtliAAOIqFiCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCAACJAAAEEEEAAAQQQQAABBBBAAAEEEEAAAQQQQAABBBBAAAEEEED0P4GEDy9er4eAAAJIxccovb8ZxxeAAALIlo+LtJ2uZkg9TU/hnYIAAWQfkHp0TBVFYRgWLKL0eg2kHdtiAXKaQG467c6/103//mZZYdxO02JfFaWjgkq510rTEBBAThJI95jOt4DUruM43kyQ6/L0Ef11HAEEEFuscou1PoNEnW4UpsUeqw4IIA7p21exypPHaFT8SOPQBAEEkD2Pg6w+TSTyOAgggJx4gAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAACCCCACBBAAAEEEEAAAQQQQAABBBBAAAEEEEAAAQQQQAABBBBAAAEEEEAA2QFSi8JqgAACyD2QUe2iGiCAALKq3r453+kqjQABROsJEo/iatcmCCBwbICEUb2aLRYggLiKBQgggAACCCCAAAIIIIAAAggggAACCCCAAAIIIIAAAggggAgQQAABBBBAAAEEEEC+J5C7T7+qrH1lDTZ9ugPkAcjnuxcq+vjhjxcfLcOqu8+APPSL1r17bw0eqt5LnjGQV1r15t37lxZj02tAVKkE8sYyHAgQQAABBBBAAAEEEEAAAQQQQB4XyJs9WRhAtAHybqe3vxECiEofBZC3O/0OyHMD8lL7e12eQXayLpsAAeT9y1eW4ZkDufxyqQNNlhbncF8unwUQHS4ZDC3CUwoQQAQIIAIEEAECiAABRIAIEEAECCACBBABAogAESCACBBABAggAgQQASJAABEggAgQQAQIIAIEEIsAiAD5WYA0Ws1qLesCiNZAZr2dBgvrAog2E2Te6Fea+xcBImcQQAQIIAIEEAECiAABBBBABAggAgQQAQKIAAFEgAgQQAQIIAIEEAECiADRFhAvVwNE/wDEGgAiQAARIIAIEEAECCACRIAAIkAAESCA6BGAzKbJtNKkb10A0QbIZLe5dQFEtliACBBABAggAgQQPUbDs1bQOmsBAoj2NVkmwXQ5BeRJ1gLkRzdfToLxrA/I0wyQH7i5Kiq2VovBZDB3BgFE2zV6495gUqq4zRzSAVF1gCwWi7wcHfNxAxBAdKCzbJCfAQKI9jddjpcJIIBof81+o2+CAKIjAgQQAQKIAAFETxTIkDJAAKme9ZPF5lYjyZqWEhBAtsdGnm9u5f15bikBAeS+Rr5YDIPG/QTJWw83BQggBZA8L4DcP+MxHzZMEEAA2a6VJ43iDyQFkDwzQQABpHJIz7NihORZ+eQuAwSQEwUy6zcbR+Q6LiDfrrPmz1KQLAfHtMyCpr798u/pT4ZTcMkcXxW8AAAAAElFTkSuQmCC" alt="The results of using homogeneous coordinates to move the boxes around in WebGL." width="800" height="530" />

### Exercises

-   Play around with these values to see how it affects what is rendered on the screen. Note how the previously clipped blue box is brought back into range by setting its w component.
-   Try creating a new box that is outside of clip space and bring it back in by dividing by w.

Model transform
---------------

Placing points directly into clip space is of limited use. In real world applications, you don't have all your source coordinates already in clip space coordinates. So most of the time, you need to transform the model data and other coordinates into clip space. The humble cube is an easy example of how to do this. Cube data consists of vertex positions, the colors of the faces of the cube, and the order of the vertex positions that make up the individual polygons (in groups of 3 vertices to construct the triangles composing the cube's faces). The positions and colors are stored in GL buffers, sent to the shader as attributes, and then operated upon individually.

Finally a single model matrix is computed and set. This matrix represents the transformations to be performed on every point making up the model in order to move it into the correct space, and to perform any other needed transforms on each point in the model. This applies not just to each vertex, but to every single point on every surface of the model as well.

In this case, for every frame of the animation a series of scale, rotation, and translation matrices move the data into the desired spot in clip space. The cube is the size of clip space (-1,-1,-1) to (1,1,1) so it will need to be shrunk down in order to not fill the entirety of clip space. This matrix is sent directly to the shader, having been multiplied in JavaScript beforehand.

The following code sample defines a method on the `CubeDemo` object that will create the model matrix. It uses custom functions to create and multiply matrices as defined in the [MDN WebGL](https://github.com/TatumCreative/mdn-webgl) shared code. The new function looks like this:

    CubeDemo.prototype.computeModelMatrix = function(now) {
      //Scale down by 50%
      var scale = MDN.scaleMatrix(0.5, 0.5, 0.5);

      // Rotate a slight tilt
      var rotateX = MDN.rotateXMatrix(now * 0.0003);

      // Rotate according to time
      var rotateY = MDN.rotateYMatrix(now * 0.0005);

      // Move slightly down
      var position = MDN.translateMatrix(0, -0.1, 0);

      // Multiply together, make sure and read them in opposite order
      this.transforms.model = MDN.multiplyArrayOfMatrices([
        position, // step 4
        rotateY,  // step 3
        rotateX,  // step 2
        scale     // step 1
      ]);
    };

In order to use this in the shader it must be set to a uniform location. The locations for the uniforms are saved in the `locations` object shown below:

    this.locations.model = gl.getUniformLocation(webglProgram, 'model');

And finally the uniform is set to that location. This hands off the matrix to the GPU.

    gl.uniformMatrix4fv(this.locations.model, false, new Float32Array(this.transforms.model));

In the shader, each position vertex is first transformed into a homogeneous coordinate (a `vec4` object), and then multiplied against the model matrix.

    gl_Position = model * vec4(position, 1.0);

**Note**: In JavaScript, matrix multiplication requires a custom function, while in the shader it is built into the language with the simple \* operator.

### The results

[View on JSFiddle](https://jsfiddle.net/5jofzgsh)

<img src="data:image/png;base64,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" alt="Using a model matrix" width="800" height="530" />

At this point the w value of the transformed point is still 1.0. The cube still doesn't have any perspective. The next section will take this setup and modify the w values to provide some perspective.

### Exercises

-   Shrink down the box using the scale matrix and position it in different places within clip space.
-   Try moving it outside of clip space.
-   Resize the window and watch as the box skews out of shape.
-   Add a `rotateZ` matrix.

Divide by W
-----------

An easy way to start getting some perspective on our model of the cube is to take the Z coordinate and copy it over to the w coordinate. Normally when converting a cartesian point to homogeneous it becomes `(x,y,z,1)`, but we're going to set it to something like `(x,y,z,z)`. In reality we want to make sure that z is greater than 0 for points in view, so we'll modify it slightly by changing the value to `((1.0 + z) * scaleFactor)`. This will take a point that is normally in clip space (-1 to 1) and move it into a space more like (0 to 1) depending on what the scale factor is set to. The scale factor changes the final w value to be either higher or lower overall.

The shader code looks like this.

    // First transform the point
    vec4 transformedPosition = model * vec4(position, 1.0);

    // How much effect does the perspective have?
    float scaleFactor = 0.5;

    // Set w by taking the z value which is typically ranged -1 to 1, then scale
    // it to be from 0 to some number, in this case 0-1.
    float w = (1.0 + transformedPosition.z) * scaleFactor;

    // Save the new gl_Position with the custom w component
    gl_Position = vec4(transformedPosition.xyz, w);

### The results

[View on JSFiddle](https://jsfiddle.net/vk9r8h2c)

<img src="data:image/png;base64,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" alt="Filling the W component and creating some projection." width="800" height="531" />

See that small dark blue triangle? That's an additional face added to our object because the rotation of our shape has caused that corner to extend outside clip space, thus causing the corner to be clipped away. See [Perspective projection matrix](#perspective_projection_matrix) below for an introduction to how to use more complex matrices to help control and prevent clipping.

### Exercise

If that sounds a little abstract, open up the vertex shader and play around with the scale factor and watch how it shrinks vertices more towards the surface. Completely change the w component values for really trippy representations of space.

In the next section we'll take this step of copying Z into the w slot and turn it into a matrix.

Simple projection
-----------------

The last step of filling in the w component can actually be accomplished with a simple matrix. Start with the identity matrix:

    var identity = [
      1, 0, 0, 0,
      0, 1, 0, 0,
      0, 0, 1, 0,
      0, 0, 0, 1,
    ];

    MDN.multiplyPoint(identity, [2, 3, 4, 1]);
    //> [2, 3, 4, 1]

Then move the last column's 1 up one space.

    var copyZ = [
      1, 0, 0, 0,
      0, 1, 0, 0,
      0, 0, 1, 1,
      0, 0, 0, 0,
    ];

    MDN.multiplyPoint(copyZ, [2, 3, 4, 1]);
    //> [2, 3, 4, 4]

However in the last example we performed `(z + 1) * scaleFactor`:

    var scaleFactor = 0.5;

    var simpleProjection = [
      1, 0, 0, 0,
      0, 1, 0, 0,
      0, 0, 1, scaleFactor,
      0, 0, 0, scaleFactor,
    ];

    MDN.multiplyPoint(simpleProjection, [2, 3, 4, 1]);
    //> [2, 3, 4, 2.5]

Breaking it out a little further we can see how this works:

    var x = (2 * 1) + (3 * 0) + (4 * 0) + (1 * 0)
    var y = (2 * 0) + (3 * 1) + (4 * 0) + (1 * 0)
    var z = (2 * 0) + (3 * 0) + (4 * 1) + (1 * 0)
    var w = (2 * 0) + (3 * 0) + (4 * scaleFactor) + (1 * scaleFactor)

The last line could be simplified to:

    w = (4 * scaleFactor) + (1 * scaleFactor)

Then factoring out the scaleFactor, we get this:

    w = (4 + 1) * scaleFactor

Which is exactly the same as the `(z + 1) * scaleFactor` that we used in the previous example.

In the box demo, an additional `computeSimpleProjectionMatrix()` method is added. This is called in the `draw()` method and has the scale factor passed to it. The result should be identical to the last example:

    CubeDemo.prototype.computeSimpleProjectionMatrix = function(scaleFactor) {
        this.transforms.projection = [
            1, 0, 0, 0,
            0, 1, 0, 0,
            0, 0, 1, scaleFactor,
            0, 0, 0, scaleFactor
        ];
    };

Although the result is identical, the important step here is in the vertex shader. Rather than modifying the vertex directly, it gets multiplied by an additional **[projection matrix](#projection_matrix)**, which (as the name suggests) projects 3D points onto a 2D drawing surface:

    // Make sure to read the transformations in reverse order
    gl_Position = projection * model * vec4(position, 1.0);

### The results

[View on JSFiddle](https://jsfiddle.net/zwyLLcbw)

<img src="data:image/png;base64,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" alt="A simple projection matrix" width="800" height="531" />

The viewing frustum
-------------------

Before we move on to covering how to compute a perspective projection matrix, we need to introduce the concept of the **[viewing frustum](https://en.wikipedia.org/wiki/Viewing_frustum)** (also known as the **view frustum**). This is the region of space whose contents are visible to the user at the current time. It's the 3D region of space defined by the field of view and the distances specified as the nearest and farthest content that should be rendered.

While rendering, we need to determine which polygons need to be rendered in order to represent the scene. This is what the viewing frustum defines. But what's a frustum in the first place?

A [frustum](https://en.wikipedia.org/wiki/Frustum) is the 3D solid that results from taking any solid and slicing off two sections of it using two parallel planes. Consider our camera, which is viewing an area that starts immediately in front of its lens and extends off into the distance. The viewable area is a four-sided pyramid with its peak at the lens, its four sides corresponding to the extents of its peripheral vision range, and its base at the farthest distance it can see, like this:

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI1MzEiIGhlaWdodD0iNDMyLjM2NyI+PGRlZnM+PGxpbmVhckdyYWRpZW50IGlkPSJhIiBncmFkaWVudFVuaXRzPSJ1c2VyU3BhY2VPblVzZSIgeDE9IjEwMTcuODc1IiB5MT0iMTAzNC4wNTQiIHgyPSIxMDc5LjIzNSIgeTI9IjYzNy45NDYiPjxzdG9wIG9mZnNldD0iMCIgc3RvcC1jb2xvcj0icmVkIiBzdG9wLW9wYWNpdHk9Ii41NiIvPjxzdG9wIG9mZnNldD0iLjgzOCIgc3RvcC1jb2xvcj0icmVkIiBzdG9wLW9wYWNpdHk9Ii41NiIvPjxzdG9wIG9mZnNldD0iMSIgc3RvcC1jb2xvcj0iI0ZGRiIgc3RvcC1vcGFjaXR5PSIuNTYiLz48L2xpbmVhckdyYWRpZW50PjxsaW5lYXJHcmFkaWVudCBpZD0iYiIgZ3JhZGllbnRVbml0cz0idXNlclNwYWNlT25Vc2UiIHgxPSI4MzcuNjU2IiB5MT0iOTAyLjM1NSIgeDI9IjEzMTEuNDUzIiB5Mj0iODAwLjY0NSI+PHN0b3Agb2Zmc2V0PSIwIiBzdG9wLWNvbG9yPSIjMEYwIiBzdG9wLW9wYWNpdHk9Ii41NiIvPjxzdG9wIG9mZnNldD0iLjc1MSIgc3RvcC1jb2xvcj0iIzBGMCIgc3RvcC1vcGFjaXR5PSIuNTYiLz48c3RvcCBvZmZzZXQ9IjEiIHN0b3AtY29sb3I9IiNGRkYiIHN0b3Atb3BhY2l0eT0iLjU2Ii8+PC9saW5lYXJHcmFkaWVudD48L2RlZnM+PGcgc3Ryb2tlPSIjMDAwIiBzdHJva2UtZGFzaGFycmF5PSIzLDIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZmlsbD0ibm9uZSI+PHBhdGggZD0iTTM2LjYwOSA0MDIuNWwxODAtNDAwIi8+PHBhdGggZD0iTTM2LjYwOSA0MDIuNWwyNDguODkxLTE2NyIgc3Ryb2tlLW9wYWNpdHk9Ii4zNSIvPjxwYXRoIGQ9Ik0zNi42MDkgNDAyLjVMNTI1LjIxIDI4NC40TTM2LjYwOSA0MDIuNUw0NzcuNSAzMy41Ii8+PC9nPjxwYXRoIGQ9Ik0wIDQxNi41NjJsMTkuNzU2LTE1LjMyIDEyLjI1NiAxNS44MDYtMTkuNzU2IDE1LjMxOXoiLz48cGF0aCBkPSJNMjMuNTEzIDQxMC45ODNsNi41NDctMTYuMDM1IDEwLjYxNCAxMy42ODd6Ii8+PHBhdGggZD0iTTgyOC4xMDkgMTAzNmwxODAtNDAwTDEyNjkgNjY3eiIgZmlsbD0idXJsKCNhKSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTc5MiAtNjM0KSIvPjxwYXRoIGQ9Ik0zNS42MDkgNDAyLjVsMTgwLTQwMG0yNjAuODkxIDMxbC00NDAuODkxIDM2OSIgc3Ryb2tlPSIjMDAwIiBzdHJva2Utd2lkdGg9IjMiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZmlsbD0ibm9uZSIvPjxwYXRoIGQ9Ik0xMzIxIDkxOGwtNTItMjUxLTQ0MC44OTEgMzY5eiIgZmlsbD0idXJsKCNiKSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTc5MiAtNjM0KSIvPjxwYXRoIGQ9Ik00NzcuNSAzMi41bC00NDAuODkxIDM2OW0uMDAxIDBsNDkyLjg5LTExOCIgc3Ryb2tlPSIjMDAwIiBzdHJva2Utd2lkdGg9IjMiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZmlsbD0ibm9uZSIvPjxwYXRoIGQ9Ik0yMTYuNjA5IDIuNWw2OC44OTEgMjMzIDI0NCA0OS01Mi0yNTF6IiBzdHJva2U9IiMwMDAiIHN0cm9rZS1vcGFjaXR5PSIuMzU0IiBzdHJva2UtZGFzaGFycmF5PSIzLDIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZmlsbD0ibm9uZSIvPjwvc3ZnPg==" alt="A depiction of the entire viewing area of a camera. This area is a four-sided pyramid with its peak at the lens and its base at the world&#39;s maximum viewable distance." width="531" height="432" />

If we used this to determine the polygons to be rendered each frame, our renderer would need to render every polygon within this pyramid, all the way off into infinity, including also polygons that are very close to the lens—likely too close to be useful (and certainly including things that are so close that a real human wouldn't be able to focus on them in the same setting).

So the first step in reducing the number of polygons we need to compute and render, we turn this pyramid into the viewing frustum. The two planes we'll use to chop away vertices in order to reduce the polygon count are the **near clipping plane** and the **far clipping plane**.

In WebXR, the near and far clipping planes are defined by specifying the distance from the lens to the closest point on a plane which is perpendicular to the viewing direction. Anything closer to the lens than the near clipping plane or farther from it than the far clipping plane is removed. This results in the viewing frustum, which looks like this:

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI1NDQiIGhlaWdodD0iNDMxLjM2NyI+PHBhdGggZD0iTTAgNDE1LjU2MmwxOS43NTYtMTUuMzE5IDEyLjI1NiAxNS44MDUtMTkuNzU2IDE1LjMxOXoiLz48cGF0aCBkPSJNMjMuNTEzIDQwOS45ODNsNi41NDctMTYuMDM1IDEwLjYxNCAxMy42ODh6Ii8+PHBhdGggZD0iTTM2LjYwOSA0MDEuNWwxODAtNDAwbS0xODAgNDAwbDI4Ni4wNjItMTk0LjA3NU0zNi42MDkgNDAxLjVMNTI1LjIxIDI4My40TTM2LjYwOSA0MDEuNWw0MzguOTctMzc2LjE2NCIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtZGFzaGFycmF5PSIzLDIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZmlsbD0ibm9uZSIvPjxwYXRoIGQ9Ik0xOTYuNjA5IDQ2LjVsNjYuNTMzIDIwMS43NzhMNDU1LjYwOSAzMDAuNWwtNDgtMjE3eiIgZmlsbD0iI0NDQyIgZmlsbC1vcGFjaXR5PSIuNTU5Ii8+PHBhdGggZD0iTTE5Ni42MDkgNDYuNWw2Ni41MzMgMjAxLjc3OEw0NTUuNjA5IDMwMC41bC00OC0yMTd6IiBzdHJva2U9IiMwMDAiIHN0cm9rZS13aWR0aD0iMyIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBmaWxsPSJub25lIi8+PHBhdGggZD0iTTEwMS42MDkgMjU3LjVsOTUtMjExIDIxMSAzNy0yMzcgMjAzeiIgZmlsbD0icmVkIiBmaWxsLW9wYWNpdHk9Ii41NTkiLz48cGF0aCBkPSJNMTAxLjYwOSAyNTcuNWw5NS0yMTEgMjExIDM3LTIzNyAyMDN6IiBzdHJva2U9IiMwMDAiIHN0cm9rZS13aWR0aD0iMyIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBmaWxsPSJub25lIi8+PHBhdGggZD0iTTQ1NS42MDkgMzAwLjVsLTQ4LTIxNy0yMzcgMjAzIDI3IDc3eiIgZmlsbD0iIzBGMCIgZmlsbC1vcGFjaXR5PSIuNTU5Ii8+PHBhdGggZD0iTTQ1NS42MDkgMzAwLjVsLTQ4LTIxNy0yMzcgMjAzIDI3IDc3eiIgc3Ryb2tlPSIjMDAwIiBzdHJva2Utd2lkdGg9IjMiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZmlsbD0ibm9uZSIvPjxwYXRoIGQ9Ik0xMDEuNjA5IDI1Ny41bDY5IDI5IDI3IDc3LTY4LjY5OS0yNC42MTF6IiBmaWxsPSIjRkYwIiBmaWxsLW9wYWNpdHk9Ii41NTkiLz48cGF0aCBkPSJNMTAxLjYwOSAyNTcuNWw2OSAyOSAyNyA3Ny02OC42OTktMjQuNjExeiIgc3Ryb2tlPSIjMDAwIiBzdHJva2Utd2lkdGg9IjMiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZmlsbD0ibm9uZSIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDIxOS44OTUgMzg5LjMwMikiPjx0c3BhbiB4PSItNjAuMzUiIHk9IjQiIGZvbnQtZmFtaWx5PSJBcmlhbE1UIiBmb250LXNpemU9IjIyIj5OZWFyIFBsYW5lPC90c3Bhbj48L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNDgzLjY1IDkzKSI+PHRzcGFuIHg9Ii02MC4zNSIgeT0iNCIgZm9udC1mYW1pbHk9IkFyaWFsTVQiIGZvbnQtc2l6ZT0iMjIiPkZhciBQbGFuZTwvdHNwYW4+PC90ZXh0Pjwvc3ZnPg==" alt="A depiction of the camera&#39;s view frustum; the near and far planes have removed part of the volume, reducing the polygon count." width="544" height="431" />

The set of objects to be rendered for each frame is essentially created by starting with the set of all objects in the scene. Then any objects which are *entirely* outside the viewing frustum are removed from the set. Next, objects which partially extrude outside the viewing frustum are clipped by dropping any polygons which are entirely outside the frustum, and by clipping the polygons which cross outside the frustrum so that they no longer exit it.

Once that's been done, we have the largest set of polygons which are entirely within the viewing frustum. This list is usually further reduced using processes like [back-face culling](https://en.wikipedia.org/wiki/Back-face_culling) (removing polygons whose back side is facing the camera) and occlusion culling using [hidden-surface determination](https://en.wikipedia.org/wiki/Hidden-surface_determination) (removing polygons which can't be seen because they're entirely blocked by polygons that are closer to the lens).

Perspective projection matrix
-----------------------------

Up to this point, we've built up our own 3D rendering setup, step by step. However the current code as we've built it has some issues. For one, it gets skewed whenever we resize our window. Another is that our simple projection doesn't handle a wide range of values for the scene data. Most scenes don't work in clip space. It would be helpful to define what distance is relevant to the scene so that precision isn't lost in converting the numbers. Finally it's very helpful to have a fine-tuned control over what points get placed inside and outside of clip space. In the previous examples the corners of the cube occasionally get clipped.

The **perspective projection matrix** is a type of projection matrix that accomplishes all of these requirements. The math also starts to get a bit more involved and won't be fully explained in these examples. In short, it combines dividing by w (as done with the previous examples) with some ingenious manipulations based on [similar triangles](https://en.wikipedia.org/wiki/Similarity_%28geometry%29). If you want to read a full explanation of the math behind it check out some of the following links:

-   [OpenGL Projection Matrix](https://www.songho.ca/opengl/gl_projectionmatrix.html)
-   [Perspective Projection](http://ogldev.atspace.co.uk/www/tutorial12/tutorial12.html)
-   [Trying to understand the math behind the perspective projection matrix in WebGL](https://stackoverflow.com/questions/28286057/trying-to-understand-the-math-behind-the-perspective-matrix-in-webgl/28301213#28301213)

One important thing to note about the perspective projection matrix used below is that it flips the z axis. In clip space the z+ goes away from the viewer, while with this matrix it comes towards the viewer.

The reason to flip the z axis is that the clip space coordinate system is a left-handed coordinate system (wherein the z-axis points away from the viewer and into the screen), while the convention in mathematics, physics and 3D modeling, as well as for the view/eye coordinate system in OpenGL, is to use a right-handed coordinate system (z-axis points out of the screen towards the viewer) . More on that in the relevant Wikipedia articles: [Cartesian coordinate system](https://en.wikipedia.org/wiki/Cartesian_coordinate_system#Orientation_and_handedness), [Right-hand rule](https://en.wikipedia.org/wiki/Right-hand_rule).

Let's take a look at a `perspectiveMatrix()` function, which computes the perspective projection matrix.

    MDN.perspectiveMatrix = function(fieldOfViewInRadians, aspectRatio, near, far) {
      var f = 1.0 / Math.tan(fieldOfViewInRadians / 2);
      var rangeInv = 1 / (near - far);

      return [
        f / aspectRatio, 0,                          0,   0,
        0,               f,                          0,   0,
        0,               0,    (near + far) * rangeInv,  -1,
        0,               0,  near * far * rangeInv * 2,   0
      ];
    }

The four parameters into this function are:

`fieldOfviewInRadians`  
An angle, given in radians, indicating how much of the scene is visible to the viewer at once. The larger the number is, the more is visible by the camera. The geometry at the edges becomes more and more distorted, equivalent to a wide angle lens. When the field of view is larger, the objects typically get smaller. When the field of view is smaller, then the camera can see less and less in the scene. The objects are distorted much less by perspective and objects seem much closer to the camera

`aspectRatio`  
The scene's aspect ratio, which is equivalent to its width divided by its height. In these examples, that's the window's width divided by the window height. The introduction of this parameter finally solves the problem wherein the model gets warped as the canvas is resized and reshaped.

`nearClippingPlaneDistance`  
A positive number indicating the distance into the screen to a plane which is perpendicular to the floor, nearer than which everything gets clipped away. This is mapped to -1 in clip space, and should not be set to 0.

`farClippingPlaneDistance`  
A positive number indicating the distance to the plane beyond which geometry is clipped away. This is mapped to 1 in clip space. This value should be kept reasonably close to the distance of the geometry in order to avoid precision errors creeping in while rendering.

In the latest version of the box demo, the `computeSimpleProjectionMatrix()` method has been replaced with the `computePerspectiveMatrix()` method.

    CubeDemo.prototype.computePerspectiveMatrix = function() {
      var fieldOfViewInRadians = Math.PI * 0.5;
      var aspectRatio = window.innerWidth / window.innerHeight;
      var nearClippingPlaneDistance = 1;
      var farClippingPlaneDistance = 50;

      this.transforms.projection = MDN.perspectiveMatrix(
        fieldOfViewInRadians,
        aspectRatio,
        nearClippingPlaneDistance,
        farClippingPlaneDistance
      );
    };

The shader code is identical to the previous example:

    gl_Position = projection * model * vec4(position, 1.0);

Additionally (not shown), the position and scale matrices of the model have been changed to take it out of clip space and into the larger coordinate system.

### The results

[View on JSFiddle](https://jsfiddle.net/Lzxw7e1q)

<img src="data:image/png;base64,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" alt="A true perspective matrix" width="800" height="531" />

### Exercises

-   Experiment with the parameters of the perspective projection matrix and the model matrix.
-   Swap out the perspective projection matrix to use [orthographic projection](https://en.wikipedia.org/wiki/Orthographic_projection). In the MDN WebGL shared code you'll find the `MDN.orthographicMatrix()`. This can replace the `MDN.perspectiveMatrix()` function in `CubeDemo.prototype.computePerspectiveMatrix()`.

View matrix
-----------

While some graphics libraries have a virtual camera that can be positioned and pointed while composing a scene, OpenGL (and by extension WebGL) does not. This is where the **view matrix** comes in. Its job is to translate, rotate, and scale the objects in the scene so that they are located in the right place relative to the viewer given the viewer's position and orientation.

### Simulating a camera

This makes use of one of the fundamental facets of Einstein's special relativity theory: the principle of reference frames and relative motion says that, from the perspective of a viewer, you can simulate changing the position and orientation of the viewer by applying the opposite change to the objects in the scene. Either way, the result appears to be identical to the viewer.

Consider a box sitting on a table and a camera resting on the table one meter away, pointed at the box, the front of which is pointed toward the camera. Then consider moving the camera away from the box until it's two meters away (by adding a meter to the camera's Z position), then sliding it 10 centimeters to the its left. The box recedes from the camera by that amount and slides to the right slightly, thereby appearing smaller to the camera and exposing a small amount of its left side to the camera.

Now let's reset the scene, placing the box back in its starting point, with the camera two meters from, and directly facing, the box. This time, however, the camera is locked down on the table and cannot be moved or turned. This is what working in WebGL is like. So how do we simulate moving the camera through space?

Instead of moving the camera backward and to the left, we apply the inverse transform to the box: we move the *box* backward one meter, and then 10 centimeters to its right. The result, from the perspective of each of the two objects, is identical.

**&lt;&lt;&lt; insert image(s) here &gt;&gt;&gt;**

The final step in all of this is to create the **view matrix**, which transforms the objects in the scene so they're positioned to simulate the camera's current location and orientation. Our code as it stands can move the cube around in world space and project everything to have perspective, but we still can't move the camera.

Imagine shooting a movie with a physical camera. You have the freedom to place the camera essentially anywhere you wish, and to aim the camera in whichever direction you choose. To simulate this in 3D graphics, we use a view matrix to simulate the position and rotation of that physical camera.

Unlike the model matrix, which directly transforms the model vertices, the view matrix moves an abstract camera around. In reality, the vertex shader is still only moving the models while the "camera" stays in place. In order for this to work out correctly, the inverse of the transform matrix must be used. The inverse matrix essentially reverses a transformation, so if we move the camera view forward, the inverse matrix causes the objects in the scene to move back.

The following `computeViewMatrix()` method animates the view matrix by moving it in and out, and left and right.

    CubeDemo.prototype.computeViewMatrix = function(now) {
      var moveInAndOut = 20 * Math.sin(now * 0.002);
      var moveLeftAndRight = 15 * Math.sin(now * 0.0017);

      // Move the camera around
      var position = MDN.translateMatrix(moveLeftAndRight, 0, 50 + moveInAndOut );

      // Multiply together, make sure and read them in opposite order
      var matrix = MDN.multiplyArrayOfMatrices([
        // Exercise: rotate the camera view
        position
      ]);

      // Inverse the operation for camera movements, because we are actually
      // moving the geometry in the scene, not the camera itself.
      this.transforms.view = MDN.invertMatrix(matrix);
    };

The shader now uses three matrices.

    gl_Position = projection * view * model * vec4(position, 1.0);

After this step, the GPU pipeline will clip the out of range vertices, and send the model down to the fragment shader for rasterization.

### The results

[View on JSFiddle](https://jsfiddle.net/86fd797g)

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAyAAAAITCAMAAADIN4jtAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAEUUExURf//////LTf//0c/////MTv//0pA/z7/////NEpC/0c8//7/PEX//k1G//v9/1VP/v//+f//Tlf///Ly/2n/////4f//7u3//+L//+bm//b//728/3z/////0v//wf//kP//bqf//2Bb/9va/43/////oav/mkDs//X9Rf//X0pe/8X/fv//fkeY/3v/ynZy/2pm/+j/Vj74/0z//EpO/62r/5L/tMT/////sZaT/9j/aOTmXVT/7s7N/4mG/0lw/76/i7T//6Kf/19a8EPP/0iB/4B+/9LTdPDyTULe/2n/3EW+/9f//5n//3d12J+frUau/3Nw78v//1//5ISCytH//5GQvLv//66unWpn5Ly8v6//zN528AgAABr9SURBVHja7J3dairLFkZ3N1VUgY2sJZ6tiGdnCSZkYRBE0I3kJrdBbwwhF+f93+N0teZvRRM1dnfVrDEeweRjzDl7VtVffwEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAICHdHr8BgAfaDZ73fndYPi///BbALzS6/U6j3k0+u12q5WlVxd/85sAFNHodJe5NPp5MqaZTlOt09tR4+IHPw1E3mh0ukU91c+dkRmTumyYHK1n18nP//IDQazSyJOxnhfSyPJoFNbYZKMgF0iiLAqBGK3RzTuNVR6NaW4KJ4t30diQC0RZFAKRWWP5+DRYuSbcuFJqVzK2+cgFYq1q3DDJghhodvJyatB30Uhdn5HuS8Y2H2acC8TapHHJbweCc9Hs9bq5NIrxVGbSlx78C/IORLmAWPWLIgtERqPX6XTng9UwT0ZrqotkHBKNbUDurxNbBERd8FuCsEaj2y06DfdJ43k8ZY5Cm1mjEEheZP1GISAnGsv1UzGecpPbPwa3xwTkucLKFZLQhUDwuGS4eqpffO3TWp8ajWeBbCusQiH//OAHhoCjMR9sPvfpF8z3eCOQIiGMeiHEgmpZrIjk0di24GeIxkeB5EWWvUQhEAxuGT2PxsolY5ql6Qk9+NcCeZOPPCEoBIJQ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" alt="The view matrix" width="800" height="531" />

### Relating the coordinate systems

At this point it would be beneficial to take a step back and look at and label the various coordinate systems we use. First off, the cube's vertices are defined in **model space**. To move the model around the scene. these vertices need to be converted into **world space** by applying the model matrix.

model space → model matrix → world space

The camera hasn't done anything yet, and the points need to be moved again. Currently they are in world space, but they need to be moved to **view space** (using the view matrix) in order to represent the camera placement.

world space → view matrix → view space

Finally a **projection** (in our case the perspective projection matrix) needs to be added in order to map the world coordinates into clip space coordinates.

view space → projection matrix → clip space

### Exercise

-   Move the camera around the scene.
-   Add some rotation matrices to the view matrix to look around.
-   Finally, track the mouse's position. Use 2 rotation matrices to have the camera look up and down based on where the user's mouse is on the screen.

See also
--------

-   [WebGL](../webgl_api)
-   [3D projection](https://en.wikipedia.org/wiki/3D_projection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/WebGL_model_view_projection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/WebGL_model_view_projection</a>
