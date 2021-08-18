WebGLRenderingContext.getExtension()
====================================

The `WebGLRenderingContext.getExtension()` method enables a [WebGL](../webgl_api) extension.

Syntax
------

    gl.getExtension(name);

### Parameters

name  
A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) for the name of the WebGL extension to enable.

### Return value

A WebGL extension object, or [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) if name does not match (case-insensitive) to one of the strings in [`WebGLRenderingContext.getSupportedExtensions`](getsupportedextensions).

Examples
--------

Once a WebGL extension is enabled, you are able to use the methods, properties or constants that this extension object provides.

    var canvas = document.getElementById('canvas');
    gl = canvas.getContext('webgl');

    gl.getExtension('WEBGL_lose_context').loseContext();

WebGL extensions
----------------

Extensions for the WebGL API are registered in the [WebGL Extension Registry](https://www.khronos.org/registry/webgl/extensions/). The current extensions are:

-   [`ANGLE_instanced_arrays`](../angle_instanced_arrays)
-   [`EXT_blend_minmax`](../ext_blend_minmax)
-   [`EXT_color_buffer_float`](../ext_color_buffer_float)
-   [`EXT_color_buffer_half_float`](../ext_color_buffer_half_float)
-   [`EXT_disjoint_timer_query`](../ext_disjoint_timer_query)
-   [`EXT_float_blend`](../ext_float_blend) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
-   [`EXT_frag_depth`](../ext_frag_depth)
-   [`EXT_shader_texture_lod`](../ext_shader_texture_lod)
-   [`EXT_sRGB`](../ext_srgb)
-   [`EXT_texture_compression_bptc`](../ext_texture_compression_bptc)
-   [`EXT_texture_compression_rgtc`](../ext_texture_compression_rgtc)
-   [`EXT_texture_filter_anisotropic`](../ext_texture_filter_anisotropic)
-   [`EXT_texture_norm16`](../ext_texture_norm16)
-   [`KHR_parallel_shader_compile`](../khr_parallel_shader_compile)
-   [`OES_element_index_uint`](../oes_element_index_uint)
-   [`OES_fbo_render_mipmap`](../oes_fbo_render_mipmap)
-   [`OES_standard_derivatives`](../oes_standard_derivatives)
-   [`OES_texture_float`](../oes_texture_float)
-   [`OES_texture_float_linear`](../oes_texture_float_linear)
-   [`OES_texture_half_float`](../oes_texture_half_float)
-   [`OES_texture_half_float_linear`](../oes_texture_half_float_linear)
-   [`OES_vertex_array_object`](../oes_vertex_array_object)
-   [`OVR_multiview2`](../ovr_multiview2)
-   [`WEBGL_color_buffer_float`](../webgl_color_buffer_float)
-   [`WEBGL_compressed_texture_astc`](../webgl_compressed_texture_astc)
-   [`WEBGL_compressed_texture_atc`](../webgl_compressed_texture_atc)<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
-   [`WEBGL_compressed_texture_etc`](../webgl_compressed_texture_etc)
-   [`WEBGL_compressed_texture_etc1`](../webgl_compressed_texture_etc1)
-   [`WEBGL_compressed_texture_pvrtc`](../webgl_compressed_texture_pvrtc)
-   [`WEBGL_compressed_texture_s3tc`](../webgl_compressed_texture_s3tc)
-   [`WEBGL_compressed_texture_s3tc_srgb`](../webgl_compressed_texture_s3tc_srgb)
-   [`WEBGL_debug_renderer_info`](../webgl_debug_renderer_info)
-   [`WEBGL_debug_shaders`](../webgl_debug_shaders)
-   [`WEBGL_depth_texture`](../webgl_depth_texture)
-   [`WEBGL_draw_buffers`](../webgl_draw_buffers)
-   [`WEBGL_lose_context`](../webgl_lose_context)
-   [`WEBGL_multi_draw`](../webgl_multi_draw)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.14">WebGL 1.0<br />
<span class="small">The definition of 'WebGLRenderingContext.getExtension' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [`WebGLRenderingContext.getSupportedExtensions()`](getsupportedextensions)
-   [webglreport.com](https://webglreport.com)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getExtension" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getExtension</a>
