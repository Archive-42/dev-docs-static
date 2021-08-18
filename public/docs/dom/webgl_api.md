WebGL: 2D and 3D graphics for the web
=====================================

WebGL (Web Graphics Library) is a JavaScript API for rendering high-performance interactive 3D and 2D graphics within any compatible web browser without the use of plug-ins. WebGL does so by introducing an API that closely conforms to OpenGL ES 2.0 that can be used in HTML5 [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) elements. This conformance makes it possible for the API to take advantage of hardware graphics acceleration provided by the user's device.

Support for WebGL is present in [Firefox](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox) 4+, [Google Chrome](https://www.google.com/chrome/) 9+, [Opera](https://www.opera.com/) 12+, [Safari](https://www.apple.com/safari/) 5.1+, [Internet Explorer](https://windows.microsoft.com/en-us/internet-explorer/browser-ie) 11+, and [Microsoft Edge](https://www.microsoft.com/en-us/edge) build 10240+; however, the user's device must also have hardware that supports these features.

The [WebGL 2](#webgl_2) API introduces support for much of the OpenGL ES 3.0 feature set; it's provided through the [`WebGL2RenderingContext`](webgl2renderingcontext) interface.

The [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element is also used by the [Canvas API](canvas_api) to do 2D graphics on web pages.

Reference
---------

### Standard interfaces

-   [`WebGLRenderingContext`](webglrenderingcontext)
-   [`WebGL2RenderingContext`](webgl2renderingcontext)
-   [`WebGLActiveInfo`](webglactiveinfo)
-   [`WebGLBuffer`](webglbuffer)
-   [`WebGLContextEvent`](webglcontextevent)
-   [`WebGLFramebuffer`](webglframebuffer)
-   [`WebGLProgram`](webglprogram)
-   [`WebGLQuery`](webglquery)
-   [`WebGLRenderbuffer`](webglrenderbuffer)
-   [`WebGLSampler`](webglsampler)
-   [`WebGLShader`](webglshader)
-   [`WebGLShaderPrecisionFormat`](webglshaderprecisionformat)
-   [`WebGLSync`](webglsync)
-   [`WebGLTexture`](webgltexture)
-   [`WebGLTransformFeedback`](webgltransformfeedback)
-   [`WebGLUniformLocation`](webgluniformlocation)
-   [`WebGLVertexArrayObject`](webglvertexarrayobject)

### Extensions

-   [`ANGLE_instanced_arrays`](angle_instanced_arrays)
-   [`EXT_blend_minmax`](ext_blend_minmax)
-   [`EXT_color_buffer_float`](ext_color_buffer_float)
-   [`EXT_color_buffer_half_float`](ext_color_buffer_half_float)
-   [`EXT_disjoint_timer_query`](ext_disjoint_timer_query)
-   [`EXT_float_blend`](ext_float_blend) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
-   [`EXT_frag_depth`](ext_frag_depth)
-   [`EXT_shader_texture_lod`](ext_shader_texture_lod)
-   [`EXT_sRGB`](ext_srgb)
-   [`EXT_texture_compression_bptc`](ext_texture_compression_bptc)
-   [`EXT_texture_compression_rgtc`](ext_texture_compression_rgtc)
-   [`EXT_texture_filter_anisotropic`](ext_texture_filter_anisotropic)
-   [`EXT_texture_norm16`](ext_texture_norm16)
-   [`KHR_parallel_shader_compile`](khr_parallel_shader_compile)
-   [`OES_element_index_uint`](oes_element_index_uint)
-   [`OES_fbo_render_mipmap`](oes_fbo_render_mipmap)
-   [`OES_standard_derivatives`](oes_standard_derivatives)
-   [`OES_texture_float`](oes_texture_float)
-   [`OES_texture_float_linear`](oes_texture_float_linear)
-   [`OES_texture_half_float`](oes_texture_half_float)
-   [`OES_texture_half_float_linear`](oes_texture_half_float_linear)
-   [`OES_vertex_array_object`](oes_vertex_array_object)
-   [`OVR_multiview2`](ovr_multiview2)
-   [`WEBGL_color_buffer_float`](webgl_color_buffer_float)
-   [`WEBGL_compressed_texture_astc`](webgl_compressed_texture_astc)
-   [`WEBGL_compressed_texture_atc`](webgl_compressed_texture_atc)<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
-   [`WEBGL_compressed_texture_etc`](webgl_compressed_texture_etc)
-   [`WEBGL_compressed_texture_etc1`](webgl_compressed_texture_etc1)
-   [`WEBGL_compressed_texture_pvrtc`](webgl_compressed_texture_pvrtc)
-   [`WEBGL_compressed_texture_s3tc`](webgl_compressed_texture_s3tc)
-   [`WEBGL_compressed_texture_s3tc_srgb`](webgl_compressed_texture_s3tc_srgb)
-   [`WEBGL_debug_renderer_info`](webgl_debug_renderer_info)
-   [`WEBGL_debug_shaders`](webgl_debug_shaders)
-   [`WEBGL_depth_texture`](webgl_depth_texture)
-   [`WEBGL_draw_buffers`](webgl_draw_buffers)
-   [`WEBGL_lose_context`](webgl_lose_context)
-   [`WEBGL_multi_draw`](webgl_multi_draw)

### Events

-   [`webglcontextlost`](htmlcanvaselement/webglcontextlost_event)
-   [`webglcontextrestored`](htmlcanvaselement/webglcontextrestored_event)
-   [`webglcontextcreationerror`](htmlcanvaselement/webglcontextcreationerror_event)

### Constants and types

-   [WebGL constants](webgl_api/constants)
-   [WebGL types](webgl_api/types)

### WebGL 2

WebGL 2 is a major update to WebGL which is provided through the [`WebGL2RenderingContext`](webgl2renderingcontext) interface. It is based on OpenGL ES 3.0 and new features include:

-   [3D textures](webgl2renderingcontext/teximage3d),
-   [Sampler objects](webglsampler),
-   [Uniform Buffer objects](webgl2renderingcontext#uniform_buffer_objects),
-   [Sync objects](webglsync),
-   [Query objects](webglquery),
-   [Transform Feedback objects](webgltransformfeedback),
-   Promoted extensions that are now core to WebGL 2: [Vertex Array objects](webglvertexarrayobject), [instancing](webgl2renderingcontext/drawarraysinstanced), [multiple render targets](webgl2renderingcontext/drawbuffers), [fragment depth](ext_frag_depth).

See also the blog post ["WebGL 2 lands in Firefox"](https://hacks.mozilla.org/2017/01/webgl-2-lands-in-firefox/) and [webglsamples.org/WebGL2Samples](https://webglsamples.org/WebGL2Samples/) for a few demos.

Guides and tutorials
--------------------

Below, you'll find an assortment of guides to help you learn WebGL concepts and tutorials that offer step-by-step lessons and examples.

### Guides

[Data in WebGL](webgl_api/data)  
A guide to variables, buffers, and other types of data used when writing WebGL code.

[WebGL best practices](webgl_api/webgl_best_practices)  
Tips and suggestions to help you improve the quality, performance, and reliability of your WebGL content.

[Using extensions](webgl_api/using_extensions)  
A guide to using WebGL extensions.

### Tutorials

[WebGL tutorial](webgl_api/tutorial)  
A beginner's guide to WebGL core concepts. A good place to start if you don't have previous WebGL experience.

### Examples

[A basic 2D WebGL animation example](webgl_api/basic_2d_animation_example)  
This example demonstrates the simple animation of a one-color shape. Topics examined are adapting to aspect ratio differences, a function to build shader programs from sets of multiple shaders, and the basics of drawing in WebGL.

[WebGL by example](webgl_api/by_example)  
A series of live samples with short explanations that showcase WebGL concepts and capabilities. The examples are sorted according to topic and level of difficulty, covering the WebGL rendering context, shader programming, textures, geometry, user interaction, and more.

### Advanced tutorials

[WebGL model view projection](webgl_api/webgl_model_view_projection)  
A detailed explanation of the three core matrices that are typically used to represent a 3D object view: the model, view and projection matrices.

[Matrix math for the web](webgl_api/matrix_math_for_the_web)  
A useful guide to how 3D transform matrices work, and can be used on the web — both for WebGL calculations and in CSS3 transforms.

Resources
---------

-   [Khronos WebGL site](https://www.khronos.org/webgl/) The main web site for WebGL at the Khronos Group.
-   [WebGL Fundamentals](https://www.html5rocks.com/en/tutorials/webgl/webgl_fundamentals/) A basic tutorial with fundamentals of WebGL.
-   [Raw WebGL: An introduction to WebGL](https://www.youtube.com/embed/H4c8t6myAWU/?feature=player_detailpage) A talk by Nick Desaulniers that introduces the basics of WebGL.
-   [WebGL playground](http://webglplayground.net) An online tool for creating and sharing WebGL projects. Good for quick prototyping and experimenting.
-   [WebGL Academy](http://www.webglacademy.com) An HTML/JavaScript editor with tutorials to learn basics of webgl programming.
-   [WebGL Stats](http://webglstats.com/) A site with statistics about WebGL capabilities in browsers on different platforms.

### Libraries

-   [three.js](https://threejs.org/) is an open-source, fully featured 3D WebGL library.
-   [Babylon.js](https://www.babylonjs.com) is a powerful, simple, and open game and 3D rendering engine packed into a friendly JavaScript framework.
-   [Pixi.js](https://www.pixijs.com/) is a fast, open-source 2D WebGL renderer.
-   [Phaser](https://phaser.io/) is a fast, free and fun open source framework for Canvas and WebGL powered browser games.
-   [PlayCanvas](https://playcanvas.com/) is an open-source game engine.
-   [glMatrix](https://github.com/toji/gl-matrix) is a JavaScript matrix and vector library for high-performance WebGL apps.
-   [twgl](https://twgljs.org) is a library for making webgl less verbose.
-   [RedGL](https://github.com/redcamel/RedGL2) is an open-source 3D WebGL library.
-   [vtk.js](https://kitware.github.io/vtk-js/) is a JavaScript library for scientific visualization in your browser.
-   [webgl-lint](https://greggman.github.io/webgl-lint/) will help find errors in your WebGL code and provide useful info

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/">OpenGL ES 3.0</a></td><td><span class="spec-standard">Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/">OpenGL ES 2.0</a></td><td><span class="spec-standard">Standard</span></td><td></td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/">WebGL 2.0</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Builds on top of WebGL 1. Based on OpenGL ES 3.0.</td></tr><tr class="even"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/">WebGL 1.0</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition. Based on OpenGL ES 2.0</td></tr></tbody></table>

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

`WebGL_API`

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

`WebGL_API`

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

BCD tables only load in the browser

### WebGL 2

BCD tables only load in the browser

### Compatibility notes

In addition to the browser, the GPU itself also needs to support the feature. So, for example, S3 Texture Compression (S3TC) is only available on Tegra-based tablets. Most browsers make the WebGL context available through the `webgl` context name, but older ones need `experimental-webgl` as well. In addition, the upcoming [WebGL 2](webgl2renderingcontext) is fully backwards-compatible and will have the context name `webgl2`.

### Gecko notes

#### WebGL debugging and testing

Starting with Gecko 10.0 (Firefox 10.0 / Thunderbird 10.0 / SeaMonkey 2.7), there are two preferences available which let you control the capabilities of WebGL for testing purposes:

`webgl.min_capability_mode`  
A Boolean property that, when `true`, enables a minimum capability mode. When in this mode, WebGL is configured to only support the bare minimum feature set and capabilities required by the WebGL specification. This lets you ensure that your WebGL code will work on any device or browser, regardless of their capabilities. This is `false` by default.

`webgl.disable_extensions`  
A Boolean property that, when `true`, disables all WebGL extensions. This is `false` by default.

See also
--------

-   [Canvas API](canvas_api)
-   [Compatibility info about WebGL extensions](webglrenderingcontext/getsupportedextensions#browser_compatibility)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API</a>
