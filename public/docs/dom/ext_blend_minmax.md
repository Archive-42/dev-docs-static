EXT\_blend\_minmax
==================

The `EXT_blend_minmax` extension is part of the [WebGL API](webgl_api) and extends blending capabilities by adding two new blend equations: the minimum or maximum color components of the source and destination colors.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is only available to [WebGL1](webglrenderingcontext) contexts. In [WebGL2](webgl2renderingcontext), the functionality of this extension is available on the WebGL2 context by default. The constants in WebGL2 are `gl.MIN` and `gl.MAX`.

Constants
---------

This extension adds two new constants, which can be used in [`WebGLRenderingContext.blendEquation()`](webglrenderingcontext/blendequation) and [`WebGLRenderingContext.blendEquationSeparate()`](webglrenderingcontext/blendequationseparate):

`ext.MIN_EXT`  
Produces the minimum color components of the source and destination colors.

`ext.MAX_EXT`  
Produces the maximum color components of the source and destination colors.

Examples
--------

    var ext = gl.getExtension('EXT_blend_minmax');

    gl.blendEquation(ext.MIN_EXT);
    gl.blendEquation(ext.MAX_EXT);

    gl.blendEquationSeparate(ext.MIN_EXT, ext.MAX_EXT);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_blend_minmax/">EXT_blend_minmax<br />
<span class="small">The definition of 'EXT_blend_minmax' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`EXT_blend_minmax`

38

17

47

35-47

Not supported on Windows.

No

25

7

38

38

?

25

9

3.0

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.blendEquation()`](webglrenderingcontext/blendequation)
-   [`WebGLRenderingContext.blendEquationSeparate()`](webglrenderingcontext/blendequationseparate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_blend_minmax" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_blend_minmax</a>
