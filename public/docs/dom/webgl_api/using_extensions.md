Using WebGL extensions
======================

WebGL, like its sister APIs (OpenGL and OpenGL ES), supports extensions. A complete list of extensions is available in the [khronos webgl extension registry](https://www.khronos.org/registry/webgl/extensions/).

**Note:** In WebGL, unlike in other GL APIs, extensions are only available if explicitly requested.

Canonical extension names, vendor prefixes and preferences
----------------------------------------------------------

Extensions may be supported by browser vendors before being officially ratified (but only when they are in draft stage). In that case, their name can be prefixed by the vendor prefix (`MOZ_`, `WEBKIT_`, etc.) or the extension is only available once a browser preference has been toggled.

If you wish to work with the bleeding edge of extensions, and want to keep working on upon ratification (assuming, of course, that the extension doesn't change in incompatible ways), that you query the canonical extension name as well as the vendor extension name. For instance:

    var ext = (
      gl.getExtension('OES_vertex_array_object') ||
      gl.getExtension('MOZ_OES_vertex_array_object') ||
      gl.getExtension('WEBKIT_OES_vertex_array_object')
    );

Note that, vendor prefix have been discouraged more and more and thus most browser implement experimental extensions behind a feature flag rather than vendor prefix.

The feature flags are:

-   `webgl.enable-draft-extensions` in Firefox
-   `chrome://flags/#enable-webgl-draft-extensions` in Chromium based browsers (Chrome, Opera).

Naming conventions
------------------

WebGL extensions are prefixed with "ANGLE", "OES", "EXT" or "WEBGL". These prefixes reflect origin and intent:

-   `ANGLE_`: Extensions that are written by the [ANGLE library](https://en.wikipedia.org/wiki/ANGLE_%28software%29) authors.
-   `OES_` and `KHR_`: Extensions that mirror functionality from OpenGL ES (OES) or OpenGL API extensions approved by the respective architecture review boards (Khronos).
-   `OVR_`: Extensions that optimize for virtual reality.
-   `EXT_`: Extensions that mirror other OpenGL ES or OpenGL API extensions.
-   `WEBGL_`: Extensions that are WebGL-specific and intended to be compatible with multiple web browsers. It should also be used for extensions which originated with the OpenGL ES or OpenGL APIs, but whose behavior has been significantly altered.

Querying available extensions
-----------------------------

The WebGL context supports querying what extensions are available.

    var available_extensions = gl.getSupportedExtensions();

The [`WebGLRenderingContext.getSupportedExtensions()`](../webglrenderingcontext/getsupportedextensions) method returns an array of strings, one for each supported extension.

Extension list
--------------

The current extensions are:

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

Enabling an extension
---------------------

Before an extension can be used it has to be enabled using [`WebGLRenderingContext.getExtension()`](../webglrenderingcontext/getextension). For example:

    var float_texture_ext = gl.getExtension('OES_texture_float');

The return value is `null` if the extension is not supported, or an extension object otherwise.

Extension objects
-----------------

If an extension defines specific symbols or functions that are not available in the core specification of WebGL, they will be available on the extension object returned by the call to `gl.getExtension()`.

See also
--------

-   [`WebGLRenderingContext.getSupportedExtensions()`](../webglrenderingcontext/getsupportedextensions)
-   [`WebGLRenderingContext.getExtension()`](../webglrenderingcontext/getextension)
-   [webglreport.com](https://webglreport.com)
-   [webglstats.com](http://webglstats.com)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Using_Extensions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Using_Extensions</a>
