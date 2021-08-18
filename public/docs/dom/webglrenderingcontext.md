WebGLRenderingContext
=====================

Constants
---------

See the [WebGL constants](webgl_api/constants) page.

The WebGL context
-----------------

The following properties and methods provide general information and functionality to deal with the WebGL context:

[`WebGLRenderingContext.canvas`](webglrenderingcontext/canvas)  
A read-only back-reference to the [`HTMLCanvasElement`](htmlcanvaselement). Might be [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) if it is not associated with a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element.

 [`WebGLRenderingContext.commit()`](webglrenderingcontext/commit) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Pushes frames back to the original [`HTMLCanvasElement`](htmlcanvaselement), if the context is not directly fixed to a specific canvas.

[`WebGLRenderingContext.drawingBufferWidth`](webglrenderingcontext/drawingbufferwidth)  
The read-only width of the current drawing buffer. Should match the width of the canvas element associated with this context.

[`WebGLRenderingContext.drawingBufferHeight`](webglrenderingcontext/drawingbufferheight)  
The read-only height of the current drawing buffer. Should match the height of the canvas element associated with this context.

[`WebGLRenderingContext.getContextAttributes()`](webglrenderingcontext/getcontextattributes)  
Returns a `WebGLContextAttributes` object that contains the actual context parameters. Might return [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null), if the context is lost.

[`WebGLRenderingContext.isContextLost()`](webglrenderingcontext/iscontextlost)  
Returns `true` if the context is lost, otherwise returns `false`.

[`WebGLRenderingContext.makeXRCompatible()`](webglrenderingcontext/makexrcompatible)  
Ensures the context is compatible with the user's XR hardware, re-creating the context if necessary with a new configuration to do so. This can be used to start an application using standard 2D presentation, then transition to using a VR or AR mode later.

Viewing and clipping
--------------------

[`WebGLRenderingContext.scissor()`](webglrenderingcontext/scissor)  
Defines the scissor box.

[`WebGLRenderingContext.viewport()`](webglrenderingcontext/viewport)  
Sets the viewport.

State information
-----------------

[`WebGLRenderingContext.activeTexture()`](webglrenderingcontext/activetexture)  
Selects the active texture unit.

[`WebGLRenderingContext.blendColor()`](webglrenderingcontext/blendcolor)  
Sets the source and destination blending factors.

[`WebGLRenderingContext.blendEquation()`](webglrenderingcontext/blendequation)  
Sets both the RGB blend equation and alpha blend equation to a single equation.

[`WebGLRenderingContext.blendEquationSeparate()`](webglrenderingcontext/blendequationseparate)  
Sets the RGB blend equation and alpha blend equation separately.

[`WebGLRenderingContext.blendFunc()`](webglrenderingcontext/blendfunc)  
Defines which function is used for blending pixel arithmetic.

[`WebGLRenderingContext.blendFuncSeparate()`](webglrenderingcontext/blendfuncseparate)  
Defines which function is used for blending pixel arithmetic for RGB and alpha components separately.

[`WebGLRenderingContext.clearColor()`](webglrenderingcontext/clearcolor)  
Specifies the color values used when clearing color buffers.

[`WebGLRenderingContext.clearDepth()`](webglrenderingcontext/cleardepth)  
Specifies the depth value used when clearing the depth buffer.

[`WebGLRenderingContext.clearStencil()`](webglrenderingcontext/clearstencil)  
Specifies the stencil value used when clearing the stencil buffer.

[`WebGLRenderingContext.colorMask()`](webglrenderingcontext/colormask)  
Sets which color components to enable or to disable when drawing or rendering to a [`WebGLFramebuffer`](webglframebuffer).

[`WebGLRenderingContext.cullFace()`](webglrenderingcontext/cullface)  
Specifies whether or not front- and/or back-facing polygons can be culled.

[`WebGLRenderingContext.depthFunc()`](webglrenderingcontext/depthfunc)  
Specifies a function that compares incoming pixel depth to the current depth buffer value.

[`WebGLRenderingContext.depthMask()`](webglrenderingcontext/depthmask)  
Sets whether writing into the depth buffer is enabled or disabled.

[`WebGLRenderingContext.depthRange()`](webglrenderingcontext/depthrange)  
Specifies the depth range mapping from normalized device coordinates to window or viewport coordinates.

[`WebGLRenderingContext.disable()`](webglrenderingcontext/disable)  
Disables specific WebGL capabilities for this context.

[`WebGLRenderingContext.enable()`](webglrenderingcontext/enable)  
Enables specific WebGL capabilities for this context.

[`WebGLRenderingContext.frontFace()`](webglrenderingcontext/frontface)  
Specifies whether polygons are front- or back-facing by setting a winding orientation.

[`WebGLRenderingContext.getParameter()`](webglrenderingcontext/getparameter)  
Returns a value for the passed parameter name.

[`WebGLRenderingContext.getError()`](webglrenderingcontext/geterror)  
Returns error information.

[`WebGLRenderingContext.hint()`](webglrenderingcontext/hint)  
Specifies hints for certain behaviors. The interpretation of these hints depend on the implementation.

[`WebGLRenderingContext.isEnabled()`](webglrenderingcontext/isenabled)  
Tests whether a specific WebGL capability is enabled or not for this context.

[`WebGLRenderingContext.lineWidth()`](webglrenderingcontext/linewidth)  
Sets the line width of rasterized lines.

[`WebGLRenderingContext.pixelStorei()`](webglrenderingcontext/pixelstorei)  
Specifies the pixel storage modes

[`WebGLRenderingContext.polygonOffset()`](webglrenderingcontext/polygonoffset)  
Specifies the scale factors and units to calculate depth values.

[`WebGLRenderingContext.sampleCoverage()`](webglrenderingcontext/samplecoverage)  
Specifies multi-sample coverage parameters for anti-aliasing effects.

[`WebGLRenderingContext.stencilFunc()`](webglrenderingcontext/stencilfunc)  
Sets the both front and back function and reference value for stencil testing.

[`WebGLRenderingContext.stencilFuncSeparate()`](webglrenderingcontext/stencilfuncseparate)  
Sets the front and/or back function and reference value for stencil testing.

[`WebGLRenderingContext.stencilMask()`](webglrenderingcontext/stencilmask)  
Controls enabling and disabling of both the front and back writing of individual bits in the stencil planes.

[`WebGLRenderingContext.stencilMaskSeparate()`](webglrenderingcontext/stencilmaskseparate)  
Controls enabling and disabling of front and/or back writing of individual bits in the stencil planes.

[`WebGLRenderingContext.stencilOp()`](webglrenderingcontext/stencilop)  
Sets both the front and back-facing stencil test actions.

[`WebGLRenderingContext.stencilOpSeparate()`](webglrenderingcontext/stencilopseparate)  
Sets the front and/or back-facing stencil test actions.

Buffers
-------

[`WebGLRenderingContext.bindBuffer()`](webglrenderingcontext/bindbuffer)  
Binds a `WebGLBuffer` object to a given target.

[`WebGLRenderingContext.bufferData()`](webglrenderingcontext/bufferdata)  
Updates buffer data.

[`WebGLRenderingContext.bufferSubData()`](webglrenderingcontext/buffersubdata)  
Updates buffer data starting at a passed offset.

[`WebGLRenderingContext.createBuffer()`](webglrenderingcontext/createbuffer)  
Creates a `WebGLBuffer` object.

[`WebGLRenderingContext.deleteBuffer()`](webglrenderingcontext/deletebuffer)  
Deletes a `WebGLBuffer` object.

[`WebGLRenderingContext.getBufferParameter()`](webglrenderingcontext/getbufferparameter)  
Returns information about the buffer.

[`WebGLRenderingContext.isBuffer()`](webglrenderingcontext/isbuffer)  
Returns a Boolean indicating if the passed buffer is valid.

Framebuffers
------------

[`WebGLRenderingContext.bindFramebuffer()`](webglrenderingcontext/bindframebuffer)  
Binds a `WebGLFrameBuffer` object to a given target.

[`WebGLRenderingContext.checkFramebufferStatus()`](webglrenderingcontext/checkframebufferstatus)  
Returns the status of the framebuffer.

[`WebGLRenderingContext.createFramebuffer()`](webglrenderingcontext/createframebuffer)  
Creates a `WebGLFrameBuffer` object.

[`WebGLRenderingContext.deleteFramebuffer()`](webglrenderingcontext/deleteframebuffer)  
Deletes a `WebGLFrameBuffer` object.

[`WebGLRenderingContext.framebufferRenderbuffer()`](webglrenderingcontext/framebufferrenderbuffer)  
Attaches a `WebGLRenderingBuffer` object to a `WebGLFrameBuffer` object.

[`WebGLRenderingContext.framebufferTexture2D()`](webglrenderingcontext/framebuffertexture2d)  
Attaches a textures image to a `WebGLFrameBuffer` object.

[`WebGLRenderingContext.getFramebufferAttachmentParameter()`](webglrenderingcontext/getframebufferattachmentparameter)  
Returns information about the framebuffer.

[`WebGLRenderingContext.isFramebuffer()`](webglrenderingcontext/isframebuffer)  
Returns a Boolean indicating if the passed `WebGLFrameBuffer` object is valid.

[`WebGLRenderingContext.readPixels()`](webglrenderingcontext/readpixels)  
Reads a block of pixels from the `WebGLFrameBuffer`.

Renderbuffers
-------------

[`WebGLRenderingContext.bindRenderbuffer()`](webglrenderingcontext/bindrenderbuffer)  
Binds a `WebGLRenderBuffer` object to a given target.

[`WebGLRenderingContext.createRenderbuffer()`](webglrenderingcontext/createrenderbuffer)  
Creates a `WebGLRenderBuffer` object.

[`WebGLRenderingContext.deleteRenderbuffer()`](webglrenderingcontext/deleterenderbuffer)  
Deletes a `WebGLRenderBuffer` object.

[`WebGLRenderingContext.getRenderbufferParameter()`](webglrenderingcontext/getrenderbufferparameter)  
Returns information about the renderbuffer.

[`WebGLRenderingContext.isRenderbuffer()`](webglrenderingcontext/isrenderbuffer)  
Returns a Boolean indicating if the passed `WebGLRenderingBuffer` is valid.

[`WebGLRenderingContext.renderbufferStorage()`](webglrenderingcontext/renderbufferstorage)  
Creates a renderbuffer data store.

Textures
--------

[`WebGLRenderingContext.bindTexture()`](webglrenderingcontext/bindtexture)  
Binds a `WebGLTexture` object to a given target.

[`WebGLRenderingContext.compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d)  
Specifies a 2D texture image in a compressed format.

[`WebGLRenderingContext.compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d)  
Specifies a 2D texture sub-image in a compressed format.

[`WebGLRenderingContext.copyTexImage2D()`](webglrenderingcontext/copyteximage2d)  
Copies a 2D texture image.

[`WebGLRenderingContext.copyTexSubImage2D()`](webglrenderingcontext/copytexsubimage2d)  
Copies a 2D texture sub-image.

[`WebGLRenderingContext.createTexture()`](webglrenderingcontext/createtexture)  
Creates a `WebGLTexture` object.

[`WebGLRenderingContext.deleteTexture()`](webglrenderingcontext/deletetexture)  
Deletes a `WebGLTexture` object.

[`WebGLRenderingContext.generateMipmap()`](webglrenderingcontext/generatemipmap)  
Generates a set of mipmaps for a `WebGLTexture` object.

[`WebGLRenderingContext.getTexParameter()`](webglrenderingcontext/gettexparameter)  
Returns information about the texture.

[`WebGLRenderingContext.isTexture()`](webglrenderingcontext/istexture)  
Returns a Boolean indicating if the passed `WebGLTexture` is valid.

[`WebGLRenderingContext.texImage2D()`](webglrenderingcontext/teximage2d)  
Specifies a 2D texture image.

[`WebGLRenderingContext.texSubImage2D()`](webglrenderingcontext/texsubimage2d)  
Updates a sub-rectangle of the current `WebGLTexture`.

[`WebGLRenderingContext.texParameterf()`](webglrenderingcontext/texparameter)  
Sets texture parameters.

[`WebGLRenderingContext.texParameteri()`](webglrenderingcontext/texparameter)  
Sets texture parameters.

Programs and shaders
--------------------

[`WebGLRenderingContext.attachShader()`](webglrenderingcontext/attachshader)  
Attaches a `WebGLShader` to a `WebGLProgram`.

[`WebGLRenderingContext.bindAttribLocation()`](webglrenderingcontext/bindattriblocation)  
Binds a generic vertex index to a named attribute variable.

[`WebGLRenderingContext.compileShader()`](webglrenderingcontext/compileshader)  
Compiles a `WebGLShader`.

[`WebGLRenderingContext.createProgram()`](webglrenderingcontext/createprogram)  
Creates a `WebGLProgram`.

[`WebGLRenderingContext.createShader()`](webglrenderingcontext/createshader)  
Creates a `WebGLShader`.

[`WebGLRenderingContext.deleteProgram()`](webglrenderingcontext/deleteprogram)  
Deletes a `WebGLProgram`.

[`WebGLRenderingContext.deleteShader()`](webglrenderingcontext/deleteshader)  
Deletes a `WebGLShader`.

[`WebGLRenderingContext.detachShader()`](webglrenderingcontext/detachshader)  
Detaches a `WebGLShader`.

[`WebGLRenderingContext.getAttachedShaders()`](webglrenderingcontext/getattachedshaders)  
Returns a list of `WebGLShader` objects attached to a `WebGLProgram`.

[`WebGLRenderingContext.getProgramParameter()`](webglrenderingcontext/getprogramparameter)  
Returns information about the program.

[`WebGLRenderingContext.getProgramInfoLog()`](webglrenderingcontext/getprograminfolog)  
Returns the information log for a `WebGLProgram` object.

[`WebGLRenderingContext.getShaderParameter()`](webglrenderingcontext/getshaderparameter)  
Returns information about the shader.

[`WebGLRenderingContext.getShaderPrecisionFormat()`](webglrenderingcontext/getshaderprecisionformat)  
Returns a `WebGLShaderPrecisionFormat` object describing the precision for the numeric format of the shader.

[`WebGLRenderingContext.getShaderInfoLog()`](webglrenderingcontext/getshaderinfolog)  
Returns the information log for a `WebGLShader` object.

[`WebGLRenderingContext.getShaderSource()`](webglrenderingcontext/getshadersource)  
Returns the source code of a `WebGLShader` as a string.

[`WebGLRenderingContext.isProgram()`](webglrenderingcontext/isprogram)  
Returns a Boolean indicating if the passed `WebGLProgram` is valid.

[`WebGLRenderingContext.isShader()`](webglrenderingcontext/isshader)  
Returns a Boolean indicating if the passed `WebGLShader` is valid.

[`WebGLRenderingContext.linkProgram()`](webglrenderingcontext/linkprogram)  
Links the passed `WebGLProgram` object.

[`WebGLRenderingContext.shaderSource()`](webglrenderingcontext/shadersource)  
Sets the source code in a `WebGLShader`.

[`WebGLRenderingContext.useProgram()`](webglrenderingcontext/useprogram)  
Uses the specified `WebGLProgram` as part the current rendering state.

[`WebGLRenderingContext.validateProgram()`](webglrenderingcontext/validateprogram)  
Validates a `WebGLProgram`.

Uniforms and attributes
-----------------------

[`WebGLRenderingContext.disableVertexAttribArray()`](webglrenderingcontext/disablevertexattribarray)  
Disables a vertex attribute array at a given position.

[`WebGLRenderingContext.enableVertexAttribArray()`](webglrenderingcontext/enablevertexattribarray)  
Enables a vertex attribute array at a given position.

[`WebGLRenderingContext.getActiveAttrib()`](webglrenderingcontext/getactiveattrib)  
Returns information about an active attribute variable.

[`WebGLRenderingContext.getActiveUniform()`](webglrenderingcontext/getactiveuniform)  
Returns information about an active uniform variable.

[`WebGLRenderingContext.getAttribLocation()`](webglrenderingcontext/getattriblocation)  
Returns the location of an attribute variable.

[`WebGLRenderingContext.getUniform()`](webglrenderingcontext/getuniform)  
Returns the value of a uniform variable at a given location.

[`WebGLRenderingContext.getUniformLocation()`](webglrenderingcontext/getuniformlocation)  
Returns the location of a uniform variable.

[`WebGLRenderingContext.getVertexAttrib()`](webglrenderingcontext/getvertexattrib)  
Returns information about a vertex attribute at a given position.

[`WebGLRenderingContext.getVertexAttribOffset()`](webglrenderingcontext/getvertexattriboffset)  
Returns the address of a given vertex attribute.

[`WebGLRenderingContext.uniform[1234][fi][v]()`](webglrenderingcontext/uniform)  
Specifies a value for a uniform variable.

[`WebGLRenderingContext.uniformMatrix[234]fv()`](webglrenderingcontext/uniformmatrix)  
Specifies a matrix value for a uniform variable.

[`WebGLRenderingContext.vertexAttrib[1234]f[v]()`](webglrenderingcontext/vertexattrib)  
Specifies a value for a generic vertex attribute.

[`WebGLRenderingContext.vertexAttribPointer()`](webglrenderingcontext/vertexattribpointer)  
Specifies the data formats and locations of vertex attributes in a vertex attributes array.

Drawing buffers
---------------

[`WebGLRenderingContext.clear()`](webglrenderingcontext/clear)  
Clears specified buffers to preset values.

[`WebGLRenderingContext.drawArrays()`](webglrenderingcontext/drawarrays)  
Renders primitives from array data.

[`WebGLRenderingContext.drawElements()`](webglrenderingcontext/drawelements)  
Renders primitives from element array data.

[`WebGLRenderingContext.finish()`](webglrenderingcontext/finish)  
Blocks execution until all previously called commands are finished.

[`WebGLRenderingContext.flush()`](webglrenderingcontext/flush)  
Empties different buffer commands, causing all commands to be executed as quickly as possible.

Working with extensions
-----------------------

These methods manage WebGL extensions:

[`WebGLRenderingContext.getSupportedExtensions()`](webglrenderingcontext/getsupportedextensions)  
Returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`DOMString`](domstring) elements with all the supported WebGL extensions.

[`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)  
Returns an extension object.

Examples
--------

### WebGL context feature detection

In this first example we are going to check whether the browser supports [WebGL](https://developer.mozilla.org/en-US/docs/Glossary/WebGL). To that end we will try to obtain the [WebGL rendering context](webglrenderingcontext) from a [`canvas`](htmlcanvaselement) element. The [WebGL rendering context](webglrenderingcontext) is an interface, through which you can set and query the state of the graphics machine, send data to the WebGL, and execute draw commands.

Saving the state of the graphics machine within a single context interface is not unique to [WebGL](https://developer.mozilla.org/en-US/docs/Glossary/WebGL). This is also done in other graphics [API](https://developer.mozilla.org/en-US/docs/Glossary/API), such as the [canvas 2D rendering context](canvasrenderingcontext2d). However, the properties and variables you can tweak are different for each [API](https://developer.mozilla.org/en-US/docs/Glossary/API).

### Effect of canvas size on rendering with WebGL

With [`scissor()`](webglrenderingcontext/scissor) and [`clear()`](webglrenderingcontext/clear) we can demonstrate how the WebGL drawing buffer is affected by the size of the canvas.

The size of the first canvas is set to the styled [`Element`](element) size, determined by [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS). This is done by assigning the [`width`](htmlcanvaselement/width) and [`height`](htmlcanvaselement/height) properties of the canvas to the values of the [`clientWidth`](element/clientwidth) and [`clientHeight`](element/clientheight) properties, respectively.

In contrast, no such assignment is done for the second canvas. The internal [`width`](htmlcanvaselement/width) and [`height`](htmlcanvaselement/height) properties of the canvas remain at default values, which are different than the actual size of the canvas [`Element`](element) in the browser window.

The effect is clearly visible when using [`scissor()`](webglrenderingcontext/scissor) and [`clear()`](webglrenderingcontext/clear) to draw a square in the center of the canvas, by specifying its position and size in pixels. In the first canvas, we get the desired result. In the second, the square has the wrong shape, size, and position.

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14">WebGL 1.0<br />
<span class="small">The definition of 'WebGLRenderingContext' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`WebGLRenderingContext`

9

12

To access the WebGL context, use `experimental-webgl` rather than the standard `webgl` identifier.

4

11

To access the WebGL context, use `experimental-webgl` rather than the standard `webgl` identifier.

12

5.1

≤37

25

Yes

12

8

1.5

`activeTexture`

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

`attachShader`

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

`bindAttribLocation`

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

`bindBuffer`

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

`bindFramebuffer`

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

`bindRenderbuffer`

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

`bindTexture`

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

`blendColor`

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

`blendEquation`

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

`blendEquationSeparate`

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

`blendFunc`

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

`blendFuncSeparate`

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

`bufferData`

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

`bufferSubData`

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

`canvas`

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

`checkFramebufferStatus`

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

`clear`

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

`clearColor`

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

`clearDepth`

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

`clearStencil`

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

`colorMask`

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

`commit`

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

`compileShader`

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

`compressedTexImage2D`

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

`compressedTexSubImage2D`

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

`copyTexImage2D`

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

`copyTexSubImage2D`

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

`createBuffer`

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

`createFramebuffer`

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

`createProgram`

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

`createRenderbuffer`

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

`createTexture`

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

`cullFace`

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

`deleteBuffer`

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

`deleteFramebuffer`

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

`deleteProgram`

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

`deleteRenderbuffer`

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

`deleteShader`

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

`deleteTexture`

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

`depthFunc`

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

`depthMask`

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

`depthRange`

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

`detachShader`

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

`disable`

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

`disableVertexAttribArray`

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

`drawArrays`

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

`drawElements`

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

`drawingBufferHeight`

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

`drawingBufferWidth`

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

`enable`

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

`enableVertexAttribArray`

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

`finish`

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

`flush`

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

`framebufferRenderbuffer`

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

`framebufferTexture2D`

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

`frontFace`

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

`generateMipmap`

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

`getActiveAttrib`

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

`getActiveUniform`

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

`getAttachedShaders`

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

`getAttribLocation`

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

`getBufferParameter`

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

`getContextAttributes`

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

`getError`

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

`getExtension`

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

`getFramebufferAttachmentParameter`

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

`getParameter`

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

`getProgramInfoLog`

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

`getProgramParameter`

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

`getRenderbufferParameter`

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

`getShaderInfoLog`

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

`getShaderParameter`

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

`getShaderPrecisionFormat`

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

`getShaderSource`

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

`getSupportedExtensions`

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

`getTexParameter`

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

`getUniform`

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

`getUniformLocation`

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

`getVertexAttrib`

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

`getVertexAttribOffset`

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

`hint`

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

`isBuffer`

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

`isContextLost`

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

`isEnabled`

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

`isFramebuffer`

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

`isProgram`

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

`isRenderbuffer`

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

`isShader`

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

`isTexture`

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

`lineWidth`

No

12-79

No

11

No

No

No

No

No

No

No

No

`linkProgram`

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

`makeXRCompatible`

79

79

No

No

No

No

No

79

No

No

No

11.2

`pixelStorei`

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

`polygonOffset`

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

`readPixels`

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

`renderbufferStorage`

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

`sampleCoverage`

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

`scissor`

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

`shaderSource`

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

`stencilFunc`

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

`stencilFuncSeparate`

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

`stencilMask`

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

`stencilMaskSeparate`

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

`stencilOp`

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

`stencilOpSeparate`

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

`texImage2D`

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

`texParameterf`

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

`texParameteri`

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

`texSubImage2D`

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

`uniform1f`

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

`uniform1fv`

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

`uniform1i`

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

`uniform1iv`

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

`uniform2f`

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

`uniform2fv`

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

`uniform2i`

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

`uniform2iv`

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

`uniform3f`

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

`uniform3fv`

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

`uniform3i`

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

`uniform3iv`

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

`uniform4f`

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

`uniform4fv`

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

`uniform4i`

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

`uniform4iv`

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

`uniformMatrix2fv`

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

`uniformMatrix3fv`

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

`uniformMatrix4fv`

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

`useProgram`

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

`validateProgram`

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

`vertexAttrib1f`

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

`vertexAttrib1fv`

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

`vertexAttrib2f`

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

`vertexAttrib2fv`

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

`vertexAttrib3f`

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

`vertexAttrib3fv`

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

`vertexAttrib4f`

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

`vertexAttrib4fv`

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

`vertexAttribPointer`

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

`viewport`

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

-   [`HTMLCanvasElement`](htmlcanvaselement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext</a>
