OES\_texture\_float\_linear
===========================

The `OES_texture_float_linear` extension is part of the [WebGL API](webgl_api) and allows linear filtering with floating-point pixel types for textures.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

Linear filtering
----------------

The [`OES_texture_float`](oes_texture_float) extension alone does not allow linear filtering with floating-point textures. This extension enables this ability.

With the help of this extension, you can now set the magnification or minification filter in the [`WebGLRenderingContext.texParameter()`](webglrenderingcontext/texparameter) method to one of `gl.LINEAR`, `gl.LINEAR_MIPMAP_NEAREST`, `gl.NEAREST_MIPMAP_LINEAR`, or `gl.LINEAR_MIPMAP_LINEAR`, and use floating-point textures.

Examples
--------

    gl.getExtension('OES_texture_float');
    gl.getExtension('OES_texture_float_linear');

    var texture = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, texture);

    gl.texParameterf(gl.TEXTURE_2D, gl.TEXTURE_MAG_FILTER, gl.LINEAR);
    gl.texImage2D(gl.TEXTURE_2D, 0, gl.RGBA, gl.RGBA, gl.FLOAT, image);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/OES_texture_float_linear/">OES_texture_float_linear<br />
<span class="small">The definition of 'OES_texture_float_linear' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`OES_texture_float_linear`

29

≤18

24

11

16

8

≤37

29

?

16

8

2.0

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.texImage2D()`](webglrenderingcontext/teximage2d)
-   [`WebGLRenderingContext.texSubImage2D()`](webglrenderingcontext/texsubimage2d)
-   [`OES_texture_float`](oes_texture_float)
-   [`OES_texture_half_float`](oes_texture_half_float)
-   [`OES_texture_half_float_linear`](oes_texture_half_float_linear)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OES_texture_float_linear" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OES_texture_float_linear</a>
