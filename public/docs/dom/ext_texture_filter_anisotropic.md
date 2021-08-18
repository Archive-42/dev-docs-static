EXT\_texture\_filter\_anisotropic
=================================

The `EXT_texture_filter_anisotropic` extension is part of the [WebGL API](webgl_api) and exposes two constants for [anisotropic filtering (AF)](https://en.wikipedia.org/wiki/Anisotropic_filtering).

AF improves the quality of mipmapped texture access when viewing a textured primitive at an oblique angle. Using just mipmapping, these lookups have a tendency to average to grey.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

Constants
---------

`ext.MAX_TEXTURE_MAX_ANISOTROPY_EXT`  
This is the `pname` argument to the [`gl.getParameter()`](webglrenderingcontext/getparameter) call, and it returns the maximum available anisotropy.

`ext.TEXTURE_MAX_ANISOTROPY_EXT`  
This is the `pname` argument to the [`gl.getTexParameter()`](webglrenderingcontext/gettexparameter) and [`gl.texParameterf()`](webglrenderingcontext/texparameter) / [`gl.texParameteri()`](webglrenderingcontext/texparameter) calls and sets the desired maximum anisotropy for a texture.

Examples
--------

    var texture = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, texture);
    var ext = (
      gl.getExtension('EXT_texture_filter_anisotropic') ||
      gl.getExtension('MOZ_EXT_texture_filter_anisotropic') ||
      gl.getExtension('WEBKIT_EXT_texture_filter_anisotropic')
    );
    if (ext){
      var max = gl.getParameter(ext.MAX_TEXTURE_MAX_ANISOTROPY_EXT);
      gl.texParameterf(gl.TEXTURE_2D, ext.TEXTURE_MAX_ANISOTROPY_EXT, max);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_texture_filter_anisotropic/">EXT_texture_filter_anisotropic<br />
<span class="small">The definition of 'EXT_texture_filter_anisotropic' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`EXT_texture_filter_anisotropic`

34

35

12

79

47

11

21

22

7

37

37

34

35

47

21

22

7

3.0

4.0

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_texture_filter_anisotropic" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_texture_filter_anisotropic</a>
