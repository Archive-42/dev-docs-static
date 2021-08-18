WEBGL\_depth\_texture
=====================

The `WEBGL_depth_texture` extension is part of the [WebGL API](webgl_api) and defines 2D depth and depth-stencil textures.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is only available to [WebGL1](webglrenderingcontext) contexts. In [WebGL2](webgl2renderingcontext), the functionality of this extension is available on the WebGL2 context by default. The constant in WebGL2 is `gl.UNSIGNED_INT_24_8`.

Constants
---------

This extension adds a new constant:

`ext.UNSIGNED_INT_24_8_WEBGL`  
Unsigned integer type for 24-bit depth texture data.

Extended methods
----------------

This extension extends [`WebGLRenderingContext.texImage2D()`](webglrenderingcontext/teximage2d):

-   The `format` and `internalformat` parameters now accept `gl.DEPTH_COMPONENT` and `gl.DEPTH_STENCIL`.
-   The `type` parameter now accepts `gl.UNSIGNED_SHORT`, `gl.UNSIGNED_INT`, and `ext.UNSIGNED_INT_24_8_WEBGL`.
-   The `pixels` parameter now accepts an `ArrayBufferView` of type `Uint16Array` and `Uint32Array`.

This extension extends [`WebGLRenderingContext.framebufferTexture2D()`](webglrenderingcontext/framebuffertexture2d):

-   The `attachment` parameter now accepts `gl.DEPTH_STENCIL_ATTACHMENT`.

Incorrectly stated as the `target` parameter in the specification, see <https://www.khronos.org/bugzilla/show_bug.cgi?id=674>.

Examples
--------

    var ext = gl.getExtension('WEBGL_depth_texture');

    gl.texImage2D(gl.TEXTURE_2D, 0, gl.DEPTH_COMPONENT, 512, 512, 0, gl.DEPTH_COMPONENT, gl.UNSIGNED_SHORT, null);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_depth_texture/">WEBGL_depth_texture<br />
<span class="small">The definition of 'WEBGL_depth_texture' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WEBGL_depth_texture`

26

Yes

≤18

22

Yes-58

No

15

Yes

8

≤37

Yes

26

Yes

?

14

Yes

8

1.5

Yes

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.texImage2D()`](webglrenderingcontext/teximage2d)
-   [`WebGLRenderingContext.framebufferTexture2D()`](webglrenderingcontext/framebuffertexture2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_depth_texture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_depth_texture</a>
