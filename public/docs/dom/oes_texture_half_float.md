OES\_texture\_half\_float
=========================

The `OES_texture_half_float` extension is part of the [WebGL API](webgl_api) and adds texture formats with 16- (aka half float) and 32-bit floating-point components.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is only available to [WebGL1](webglrenderingcontext) contexts. In [WebGL2](webgl2renderingcontext), the functionality of this extension is available on the WebGL2 context by default. The constant in WebGL2 is `gl.HALF_FLOAT`.

Constants
---------

`ext.HALF_FLOAT_OES`  
Half floating-point type (16-bit).

Extended methods
----------------

This extension extends [`WebGLRenderingContext.texImage2D()`](webglrenderingcontext/teximage2d) and [`WebGLRenderingContext.texSubImage2D()`](webglrenderingcontext/texsubimage2d):

-   The `type` parameter now accepts `ext.HALF_FLOAT_OES`.

Limitation: Linear filtering
----------------------------

Linear filtering on half floating-point textures is not allowed with this extension. If you set the magnification or minification filter in the [`WebGLRenderingContext.texParameter()`](webglrenderingcontext/texparameter) method to one of `gl.LINEAR`, `gl.LINEAR_MIPMAP_NEAREST`, `gl.NEAREST_MIPMAP_LINEAR`, or `gl.LINEAR_MIPMAP_LINEAR`, and use half floating-point textures, the texture will be marked as incomplete.

To use linear filtering on half floating-point textures, enable the [`OES_texture_half_float_linear`](oes_texture_half_float_linear) extension in addition to this extension.

Half floating-point color buffers
---------------------------------

This extension implicitly enables the [`EXT_color_buffer_half_float`](ext_color_buffer_half_float) extension (if supported), which allows rendering to 16-bit floating point formats.

Examples
--------

    var ext = gl.getExtension('OES_texture_half_float');

    var texture = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, texture);

    gl.texImage2D(gl.TEXTURE_2D, 0, gl.RGBA, gl.RGBA, ext.HALF_FLOAT_OES, image);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/OES_texture_half_float/">OES_texture_half_float<br />
<span class="small">The definition of 'OES_texture_half_float' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`OES_texture_half_float`

27

≤18

29

No

15

8

≤37

27

?

14

8

1.5

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.texImage2D()`](webglrenderingcontext/teximage2d)
-   [`WebGLRenderingContext.texSubImage2D()`](webglrenderingcontext/texsubimage2d)
-   [`OES_texture_float`](oes_texture_float)
-   [`OES_texture_float_linear`](oes_texture_float_linear)
-   [`OES_texture_half_float_linear`](oes_texture_half_float_linear)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OES_texture_half_float" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OES_texture_half_float</a>
