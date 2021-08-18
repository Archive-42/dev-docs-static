WEBGL\_multi\_draw
==================

The `WEBGL_multi_draw` extension is part of the [WebGL API](webgl_api) and allows to render more than one primitive with a single function call. This can improve a WebGL application's performance as it reduces binding costs in the renderer and speeds up GPU thread time with uniform data.

When this extension is enabled:

-   New methods that handle multiple lists of arguments in one call are added (see method list below).
-   The `gl_DrawID` built-in is added to the shading language.

**Availability:** This extension is available to both, [WebGL 1](webglrenderingcontext) and [WebGL 2](webgl2renderingcontext) contexts.

In shader code, the directive `#extension GL_ANGLE_multi_draw` needs to be called to enable the extension.

This extension enables the [`ANGLE_instanced_arrays`](angle_instanced_arrays) extension implicitly.

Methods
-------

[`ext.multiDrawArraysWEBGL()`](webgl_multi_draw/multidrawarrayswebgl)  
Renders multiple primitives from array data (identical to multiple calls to [`drawArrays`](webglrenderingcontext/drawarrays)).

[`ext.multiDrawElementsWEBGL()`](webgl_multi_draw/multidrawelementswebgl)  
Renders multiple primitives from element array data (identical to multiple calls to [`drawElements`](en-us/docs/web/api/webglrenderingcontext/drawelements)).

[`ext.multiDrawArraysInstancedWEBGL()`](webgl_multi_draw/multidrawarraysinstancedwebgl)  
Renders multiple primitives from array data (identical to multiple calls to [`drawArraysInstanced`](webgl2renderingcontext/drawarraysinstanced)).

[`ext.multiDrawElementsInstancedWEBGL()`](webgl_multi_draw/multidrawelementsinstancedwebgl)  
Renders multiple primitives from element array data (identical to multiple calls to [`drawElementsInstanced`](webgl2renderingcontext/drawelementsinstanced)).

Shader extension
----------------

Note: Although the extension name is named `WEBGL_multi_draw`, the extension must be enabled with the `#extension GL_ANGLE_multi_draw` directive to use the extension in a shader.

When this extension is enabled, the `gl_DrawID` built-in can be used in shader code. For any `multi*` draw call variant, the index of the draw `i` may be read by the vertex shader as `gl_DrawID`. For non-`multi*` calls, the value of `gl_DrawID` is `0`.

    <script type="x-shader/x-vertex">
    #extension GL_ANGLE_multi_draw : require
    void main() {
      gl_Position = vec4(gl_DrawID, 0, 0, 1);
    }
    </script>

Examples
--------

### Enabling the extension

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

    let ext = gl.getExtension('WEBGL_multi_draw');

### Drawing multiple arrays

Example calls for [`ext.multiDrawArraysWEBGL()`](webgl_multi_draw/multidrawarrayswebgl) and [`ext.multiDrawArraysInstancedWEBGL()`](webgl_multi_draw/multidrawarraysinstancedwebgl):

    // multiDrawArrays variant
    // let firsts = new Int32Array(...);
    // let counts = new Int32Array(...);
    ext.multiDrawArraysWEBGL(gl.TRIANGLES, firsts, 0, counts, 0, firsts.length);

    // multiDrawArraysInstanced variant
    // let firsts = new Int32Array(...);
    // let counts = new Int32Array(...);
    // let instanceCounts = new Int32Array(...);
    ext.multiDrawArraysInstancedWEBGL(
      gl.TRIANGLES, firsts, 0, counts, 0, instanceCounts, 0, firsts.length);

### Drawing multiple elements

Example calls for [`ext.multiDrawElementsWEBGL()`](webgl_multi_draw/multidrawelementswebgl) and [`ext.multiDrawElementsInstancedWEBGL()`](webgl_multi_draw/multidrawelementsinstancedwebgl).

Assumes that the indices which have been previously uploaded to the `ELEMENT_ARRAY_BUFFER` are to be treated as `UNSIGNED_SHORT`.

    // multiDrawElements variant
    // let counts = new Int32Array(...);
    // let offsets = new Int32Array(...);
    ext.multiDrawElementsWEBGL(
      gl.TRIANGLES, counts, 0, gl.UNSIGNED_SHORT, offsets, 0, counts.length);
    }

    // multiDrawElementsInstanced variant
    // let counts = new Int32Array(...);
    // let offsets = new Int32Array(...);
    // let instanceCounts = new Int32Array(...);
    ext.multiDrawElementsInstancedWEBGL(
        gl.TRIANGLES, counts, 0, gl.UNSIGNED_SHORT, offsets, 0, instanceCounts, 0,
        counts.length);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_multi_draw/">WEBGL_multi_draw<br />
<span class="small">The definition of 'WEBGL_multi_draw' in that specification.</span></a></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `WEBGL_multi_draw`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`WebGLRenderingContext.drawArrays()`](webglrenderingcontext/drawarrays)
-   [`WebGLRenderingContext.drawElements()`](webglrenderingcontext/drawelements)
-   [`ANGLE_instanced_arrays.drawArraysInstancedANGLE()`](angle_instanced_arrays/drawarraysinstancedangle) or in WebGL 2: [`WebGL2RenderingContext.drawArraysInstanced()`](webgl2renderingcontext/drawarraysinstanced)
-   [`ANGLE_instanced_arrays.drawElementsInstancedANGLE()`](angle_instanced_arrays/drawelementsinstancedangle) or in WebGL 2: [`WebGL2RenderingContext.drawElementsInstanced()`](webgl2renderingcontext/drawelementsinstanced)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_multi_draw" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_multi_draw</a>
