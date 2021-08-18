WebGL2RenderingContext
======================

The **WebGL2RenderingContext** interface provides the OpenGL ES 3.0 rendering context for the drawing surface of an HTML [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element.

To get an object of this interface, call [`getContext()`](htmlcanvaselement/getcontext) on a `<canvas>` element, supplying "webgl2" as the argument:

    var canvas = document.getElementById('myCanvas');
    var gl = canvas.getContext('webgl2');

WebGL 2 is an extension to WebGL 1. The `WebGL2RenderingContext` interface implements all members of the [`WebGLRenderingContext`](webglrenderingcontext) interface. Some methods of the WebGL 1 context can accept additional values when used in a WebGL 2 context. You will find this info noted on the WebGL 1 reference pages.

The [WebGL tutorial](webgl_api/tutorial) has more information, examples, and resources on how to get started with WebGL.

Constants
---------

See the [WebGL constants](webgl_api/constants) page.

State information
-----------------

[`WebGL2RenderingContext.getIndexedParameter()`](webgl2renderingcontext/getindexedparameter)  
Returns the indexed value for the given `target`.

Buffers
-------

<span class="page-not-created">`WebGL2RenderingContext.bufferData()`</span>  
Initializes and creates the buffer object's data store.

<span class="page-not-created">`WebGL2RenderingContext.bufferSubData()`</span>  
Updates a subset of a buffer object's data store.

[`WebGL2RenderingContext.copyBufferSubData()`](webgl2renderingcontext/copybuffersubdata)  
Copies part of the data of a buffer to another buffer.

[`WebGL2RenderingContext.getBufferSubData()`](webgl2renderingcontext/getbuffersubdata)  
Reads data from a buffer and writes them to an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) or [`SharedArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer).

Framebuffers
------------

[`WebGL2RenderingContext.blitFramebuffer()`](webgl2renderingcontext/blitframebuffer)  
Transfers a block of pixels from the read framebuffer to the draw framebuffer.

[`WebGL2RenderingContext.framebufferTextureLayer()`](webgl2renderingcontext/framebuffertexturelayer)  
Attaches a single layer of a texture to a framebuffer.

[`WebGL2RenderingContext.invalidateFramebuffer()`](webgl2renderingcontext/invalidateframebuffer)  
Invalidates the contents of attachments in a framebuffer.

[`WebGL2RenderingContext.invalidateSubFramebuffer()`](webgl2renderingcontext/invalidatesubframebuffer)  
Invalidates portions of the contents of attachments in a framebuffer

[`WebGL2RenderingContext.readBuffer()`](webgl2renderingcontext/readbuffer)  
Selects a color buffer as the source for pixels.

Renderbuffers
-------------

[`WebGL2RenderingContext.getInternalformatParameter()`](webgl2renderingcontext/getinternalformatparameter)  
Returns information about implementation-dependent support for internal formats.

[`WebGL2RenderingContext.renderbufferStorageMultisample()`](webgl2renderingcontext/renderbufferstoragemultisample)  
Creates and initializes a renderbuffer object's data store and allows specifying the number of samples to be used.

Textures
--------

[`WebGL2RenderingContext.texStorage2D()`](webgl2renderingcontext/texstorage2d)  
Specifies all levels of two-dimensional texture storage.

[`WebGL2RenderingContext.texStorage3D()`](webgl2renderingcontext/texstorage3d)  
Specifies all levels of a three-dimensional texture or two-dimensional array texture.

[`WebGL2RenderingContext.texImage3D()`](webgl2renderingcontext/teximage3d)  
Specifies a three-dimensional texture image.

[`WebGL2RenderingContext.texSubImage3D()`](webgl2renderingcontext/texsubimage3d)  
Specifies a sub-rectangle of the current 3D texture.

[`WebGL2RenderingContext.copyTexSubImage3D()`](webgl2renderingcontext/copytexsubimage3d)  
Copies pixels from the current [`WebGLFramebuffer`](webglframebuffer) into an existing 3D texture sub-image.

[`WebGL2RenderingContext.compressedTexImage3D()`](webglrenderingcontext/compressedteximage2d)  
Specifies a three-dimensional texture image in a compressed format.

[`WebGL2RenderingContext.compressedTexSubImage3D()`](webgl2renderingcontext/compressedtexsubimage3d)  
Specifies a three-dimensional sub-rectangle for a texture image in a compressed format.

Programs and shaders
--------------------

[`WebGL2RenderingContext.getFragDataLocation()`](webgl2renderingcontext/getfragdatalocation)  
Returns the binding of color numbers to user-defined varying out variables.

Uniforms and attributes
-----------------------

[`WebGL2RenderingContext.uniform[1234][uif][v]()`](webgl2renderingcontext/uniform)  
Methods specifying values of uniform variables.

[`WebGL2RenderingContext.uniformMatrix[234]x[234]fv()`](webgl2renderingcontext/uniformmatrix)  
Methods specifying matrix values for uniform variables.

[`WebGL2RenderingContext.vertexAttribI4[u]i[v]()`](webgl2renderingcontext/vertexattribi)  
Methods specifying integer values for generic vertex attributes.

[`WebGL2RenderingContext.vertexAttribIPointer()`](webgl2renderingcontext/vertexattribipointer)  
Specifies integer data formats and locations of vertex attributes in a vertex attributes array.

Drawing buffers
---------------

[`WebGL2RenderingContext.vertexAttribDivisor()`](webgl2renderingcontext/vertexattribdivisor)  
Modifies the rate at which generic vertex attributes advance when rendering multiple instances of primitives with [`gl.drawArraysInstanced()`](webgl2renderingcontext/drawarraysinstanced) and [`gl.drawElementsInstanced()`](webgl2renderingcontext/drawelementsinstanced).

[`WebGL2RenderingContext.drawArraysInstanced()`](webgl2renderingcontext/drawarraysinstanced)  
Renders primitives from array data. In addition, it can execute multiple instances of the range of elements.

[`WebGL2RenderingContext.drawElementsInstanced()`](webgl2renderingcontext/drawelementsinstanced)  
Renders primitives from array data. In addition, it can execute multiple instances of a set of elements.

[`WebGL2RenderingContext.drawRangeElements()`](webgl2renderingcontext/drawrangeelements)  
Renders primitives from array data in a given range.

[`WebGL2RenderingContext.drawBuffers()`](webgl2renderingcontext/drawbuffers)  
Specifies a list of color buffers to be drawn into.

[`WebGL2RenderingContext.clearBuffer[fiuv]()`](webgl2renderingcontext/clearbuffer)  
Clears buffers from the currently bound framebuffer.

Query objects
-------------

Methods for working with [`WebGLQuery`](webglquery) objects.

[`WebGL2RenderingContext.createQuery()`](webgl2renderingcontext/createquery)  
Creates a new [`WebGLQuery`](webglquery) object.

[`WebGL2RenderingContext.deleteQuery()`](webgl2renderingcontext/deletequery)  
Deletes a given [`WebGLQuery`](webglquery) object.

[`WebGL2RenderingContext.isQuery()`](webgl2renderingcontext/isquery)  
Returns `true` if a given object is a valid [`WebGLQuery`](webglquery) object.

[`WebGL2RenderingContext.beginQuery()`](webgl2renderingcontext/beginquery)  
Begins an asynchronous query.

[`WebGL2RenderingContext.endQuery()`](webgl2renderingcontext/endquery)  
Marks the end of an asynchronous query.

[`WebGL2RenderingContext.getQuery()`](webgl2renderingcontext/getquery)  
Returns a [`WebGLQuery`](webglquery) object for a given target.

[`WebGL2RenderingContext.getQueryParameter()`](webgl2renderingcontext/getqueryparameter)  
Returns information about a query.

Sampler objects
---------------

[`WebGL2RenderingContext.createSampler()`](webgl2renderingcontext/createsampler)  
Creates a new [`WebGLSampler`](webglsampler) object.

[`WebGL2RenderingContext.deleteSampler()`](webgl2renderingcontext/deletesampler)  
Deletes a given [`WebGLSampler`](webglsampler) object.

[`WebGL2RenderingContext.bindSampler()`](webgl2renderingcontext/bindsampler)  
Binds a given [`WebGLSampler`](webglsampler) to a texture unit.

[`WebGL2RenderingContext.isSampler()`](webgl2renderingcontext/issampler)  
Returns `true` if a given object is a valid [`WebGLSampler`](webglsampler) object.

[`WebGL2RenderingContext.samplerParameter[if]()`](webgl2renderingcontext/samplerparameter)  
Sets sampler parameters.

[`WebGL2RenderingContext.getSamplerParameter()`](webgl2renderingcontext/getsamplerparameter)  
Returns sampler parameter information.

Sync objects
------------

[`WebGL2RenderingContext.fenceSync()`](webgl2renderingcontext/fencesync)  
Creates a new [`WebGLSync`](webglsync) object and inserts it into the GL command stream.

[`WebGL2RenderingContext.isSync()`](webgl2renderingcontext/issync)  
Returns `true` if the passed object is a valid [`WebGLSync`](webglsync) object.

[`WebGL2RenderingContext.deleteSync()`](webgl2renderingcontext/deletesync)  
Deletes a given [`WebGLSync`](webglsync) object.

[`WebGL2RenderingContext.clientWaitSync()`](webgl2renderingcontext/clientwaitsync)  
Blocks and waits for a [`WebGLSync`](webglsync) object to become signaled or a given timeout to be passed.

[`WebGL2RenderingContext.waitSync()`](webgl2renderingcontext/waitsync)  
Returns immediately, but waits on the GL server until the given [`WebGLSync`](webglsync) object is signaled.

[`WebGL2RenderingContext.getSyncParameter()`](webgl2renderingcontext/getsyncparameter)  
Returns parameter information of a [`WebGLSync`](webglsync) object.

Transform feedback
------------------

[`WebGL2RenderingContext.createTransformFeedback()`](webgl2renderingcontext/createtransformfeedback)  
Creates and initializes [`WebGLTransformFeedback`](webgltransformfeedback) objects.

[`WebGL2RenderingContext.deleteTransformFeedback()`](webgl2renderingcontext/deletetransformfeedback)  
Deletes a given [`WebGLTransformFeedback`](webgltransformfeedback) object.

[`WebGL2RenderingContext.isTransformFeedback()`](webgl2renderingcontext/istransformfeedback)  
Returns `true` if the passed object is a valid [`WebGLTransformFeedback`](webgltransformfeedback) object.

[`WebGL2RenderingContext.bindTransformFeedback()`](webgl2renderingcontext/bindtransformfeedback)  
Binds a passed [`WebGLTransformFeedback`](webgltransformfeedback) object to the current GL state.

[`WebGL2RenderingContext.beginTransformFeedback()`](webgl2renderingcontext/begintransformfeedback)  
Starts a transform feedback operation.

[`WebGL2RenderingContext.endTransformFeedback()`](webgl2renderingcontext/endtransformfeedback)  
Ends a transform feedback operation.

[`WebGL2RenderingContext.transformFeedbackVaryings()`](webgl2renderingcontext/transformfeedbackvaryings)  
Specifies values to record in [`WebGLTransformFeedback`](webgltransformfeedback) buffers.

[`WebGL2RenderingContext.getTransformFeedbackVarying()`](webgl2renderingcontext/gettransformfeedbackvarying)  
Returns information about varying variables from [`WebGLTransformFeedback`](webgltransformfeedback) buffers.

[`WebGL2RenderingContext.pauseTransformFeedback()`](webgl2renderingcontext/pausetransformfeedback)  
Pauses a transform feedback operation.

[`WebGL2RenderingContext.resumeTransformFeedback()`](webgl2renderingcontext/resumetransformfeedback)  
Resumes a transform feedback operation.

Uniform buffer objects
----------------------

[`WebGL2RenderingContext.bindBufferBase()`](webgl2renderingcontext/bindbufferbase)  
Binds a given [`WebGLBuffer`](webglbuffer) to a given binding point (`target`) at a given `index`.

[`WebGL2RenderingContext.bindBufferRange()`](webgl2renderingcontext/bindbufferrange)  
Binds a range of a given [`WebGLBuffer`](webglbuffer) to a given binding point (`target`) at a given `index`.

[`WebGL2RenderingContext.getUniformIndices()`](webgl2renderingcontext/getuniformindices)  
Retrieves the indices of a number of uniforms within a [`WebGLProgram`](webglprogram).

[`WebGL2RenderingContext.getActiveUniforms()`](webgl2renderingcontext/getactiveuniforms)  
Retrieves information about active uniforms within a [`WebGLProgram`](webglprogram).

[`WebGL2RenderingContext.getUniformBlockIndex()`](webgl2renderingcontext/getuniformblockindex)  
Retrieves the index of a uniform block within a [`WebGLProgram`](webglprogram).

[`WebGL2RenderingContext.getActiveUniformBlockParameter()`](webgl2renderingcontext/getactiveuniformblockparameter)  
Retrieves information about an active uniform block within a [`WebGLProgram`](webglprogram).

[`WebGL2RenderingContext.getActiveUniformBlockName()`](webgl2renderingcontext/getactiveuniformblockname)  
Retrieves the name of the active uniform block at a given index within a [`WebGLProgram`](webglprogram).

[`WebGL2RenderingContext.uniformBlockBinding()`](webgl2renderingcontext/uniformblockbinding)  
Assigns binding points for active uniform blocks.

Vertex array objects
--------------------

Methods for working with [`WebGLVertexArrayObject`](webglvertexarrayobject) (VAO) objects.

[`WebGL2RenderingContext.createVertexArray()`](webgl2renderingcontext/createvertexarray)  
Creates a new [`WebGLVertexArrayObject`](webglvertexarrayobject).

[`WebGL2RenderingContext.deleteVertexArray()`](webgl2renderingcontext/deletevertexarray)  
Deletes a given [`WebGLVertexArrayObject`](webglvertexarrayobject).

[`WebGL2RenderingContext.isVertexArray()`](webgl2renderingcontext/isvertexarray)  
Returns `true` if a given object is a valid [`WebGLVertexArrayObject`](webglvertexarrayobject).

[`WebGL2RenderingContext.bindVertexArray()`](webgl2renderingcontext/bindvertexarray)  
Binds a given [`WebGLVertexArrayObject`](webglvertexarrayobject) to the buffer.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7">WebGL 2.0<br />
<span class="small">The definition of 'WebGL2RenderingContext' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGL2RenderingContext`

56

79

51

No

43

No

58

58

51

43

No

7.0

`beginQuery`

56

79

51

No

43

No

58

58

51

43

No

7.0

`beginTransformFeedback`

56

79

51

No

43

No

58

58

51

43

No

7.0

`bindBufferBase`

56

79

51

No

43

No

58

58

51

43

No

7.0

`bindBufferRange`

56

79

51

No

43

No

58

58

51

43

No

7.0

`bindSampler`

56

79

51

No

43

No

58

58

51

43

No

7.0

`bindTransformFeedback`

56

79

51

No

43

No

58

58

51

43

No

7.0

`bindVertexArray`

56

79

51

No

43

No

58

58

51

43

No

7.0

`blitFramebuffer`

56

79

51

No

43

No

58

58

51

43

No

7.0

`bufferSubData`

56

79

51

No

43

No

58

58

51

43

No

7.0

`clearBufferfi`

56

79

51

No

43

No

58

58

51

43

No

7.0

`clearBufferfv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`clearBufferiv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`clearBufferuiv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`clientWaitSync`

56

79

51

No

43

No

58

58

51

43

No

7.0

`compressedTexImage3D`

56

79

51

No

43

No

58

58

51

43

No

7.0

`compressedTexSubImage3D`

56

79

51

No

43

No

58

58

51

43

No

7.0

`copyBufferSubData`

56

79

51

No

43

No

58

58

51

43

No

7.0

`copyTexSubImage3D`

56

79

51

No

43

No

58

58

51

43

No

7.0

`createQuery`

56

79

51

No

43

No

58

58

51

43

No

7.0

`createSampler`

56

79

51

No

43

No

58

58

51

43

No

7.0

`createTransformFeedback`

56

79

51

No

43

No

58

58

51

43

No

7.0

`createVertexArray`

56

79

51

No

43

No

58

58

51

43

No

7.0

`deleteQuery`

56

79

51

No

43

No

58

58

51

43

No

7.0

`deleteSampler`

56

79

51

No

43

No

58

58

51

43

No

7.0

`deleteSync`

56

79

51

No

43

No

58

58

51

43

No

7.0

`deleteTransformFeedback`

56

79

51

No

43

No

58

58

51

43

No

7.0

`deleteVertexArray`

56

79

51

No

43

No

58

58

51

43

No

7.0

`drawArraysInstanced`

56

79

51

No

43

No

58

58

51

43

No

7.0

`drawBuffers`

56

79

51

No

43

No

58

58

51

43

No

7.0

`drawElementsInstanced`

56

79

51

No

43

No

58

58

51

43

No

7.0

`drawRangeElements`

56

79

51

No

43

No

58

58

51

43

No

7.0

`endQuery`

56

79

51

No

43

No

58

58

51

43

No

7.0

`endTransformFeedback`

56

79

51

No

43

No

58

58

51

43

No

7.0

`fenceSync`

56

79

51

No

43

No

58

58

51

43

No

7.0

`framebufferTextureLayer`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getActiveUniformBlockName`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getActiveUniformBlockParameter`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getActiveUniforms`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getBufferSubData`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getFragDataLocation`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getIndexedParameter`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getInternalformatParameter`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getQuery`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getQueryParameter`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getSamplerParameter`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getSyncParameter`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getTransformFeedbackVarying`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getUniformBlockIndex`

56

79

51

No

43

No

58

58

51

43

No

7.0

`getUniformIndices`

56

79

51

No

43

No

58

58

51

43

No

7.0

`invalidateFramebuffer`

56

79

51

No

43

No

58

58

51

43

No

7.0

`invalidateSubFramebuffer`

56

79

51

No

43

No

58

58

51

43

No

7.0

`isQuery`

56

79

51

No

43

No

58

58

51

43

No

7.0

`isSampler`

56

79

51

No

43

No

58

58

51

43

No

7.0

`isSync`

56

79

51

No

43

No

58

58

51

43

No

7.0

`isTransformFeedback`

56

79

51

No

43

No

58

58

51

43

No

7.0

`isVertexArray`

56

79

51

No

43

No

58

58

51

43

No

7.0

`pauseTransformFeedback`

56

79

51

No

43

No

58

58

51

43

No

7.0

`readBuffer`

56

79

51

No

43

No

58

58

51

43

No

7.0

`renderbufferStorageMultisample`

56

79

51

No

43

No

58

58

51

43

No

7.0

`resumeTransformFeedback`

56

79

51

No

43

No

58

58

51

43

No

7.0

`samplerParameterf`

56

79

51

No

43

No

58

58

51

43

No

7.0

`samplerParameteri`

56

79

51

No

43

No

58

58

51

43

No

7.0

`texImage3D`

56

79

51

No

43

No

58

58

51

43

No

7.0

`texStorage2D`

56

79

51

No

43

No

58

58

51

43

No

7.0

`texStorage3D`

56

79

51

No

43

No

58

58

51

43

No

7.0

`texSubImage3D`

56

79

51

No

43

No

58

58

51

43

No

7.0

`transformFeedbackVaryings`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform1f`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform1i`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform1ui`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform1uiv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform2f`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform2i`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform2ui`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform2uiv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform3f`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform3i`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform3ui`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform3uiv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform4f`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform4i`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform4ui`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniform4uiv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniformBlockBinding`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniformMatrix2fv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniformMatrix2x3fv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniformMatrix2x4fv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniformMatrix3fv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniformMatrix3x2fv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniformMatrix3x4fv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniformMatrix4fv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniformMatrix4x2fv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`uniformMatrix4x3fv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`vertexAttribDivisor`

56

79

51

No

43

No

58

58

51

43

No

7.0

`vertexAttribI4i`

56

79

51

No

43

No

58

58

51

43

No

7.0

`vertexAttribI4iv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`vertexAttribI4ui`

56

79

51

No

43

No

58

58

51

43

No

7.0

`vertexAttribI4uiv`

56

79

51

No

43

No

58

58

51

43

No

7.0

`vertexAttribIPointer`

56

79

51

No

43

No

58

58

51

43

No

7.0

`waitSync`

56

79

51

No

43

No

58

58

51

43

No

7.0

See also
--------

-   [`HTMLCanvasElement`](htmlcanvaselement)
-   [`WebGLRenderingContext`](webglrenderingcontext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext</a>
