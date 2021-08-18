WEBGL\_compressed\_texture\_atc
===============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `WEBGL_compressed_texture_atc` extension is part of the [WebGL API](webgl_api) and exposes 3 ATC compressed texture formats. ATC is a proprietary compression algorithm for compressing textures on handheld devices.

Compressed textures reduce the amount of memory needed to store a texture on the GPU, allowing for higher resolution textures or more of the same resolution textures.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** ATC compression is typically available on mobile devices with [Adreno GPUs](https://en.wikipedia.org/wiki/Adreno), that are currently only built into [Qualcomm Snapdragon](https://en.wikipedia.org/wiki/Qualcomm_Snapdragon) devices.

This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

Constants
---------

The compressed texture formats are exposed by 3 constants and can be used in two functions: [`compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d) and [`compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d).

`ext.COMPRESSED_RGB_ATC_WEBGL`  
Compresses RGB textures with no alpha channel.

`ext.COMPRESSED_RGBA_ATC_EXPLICIT_ALPHA_WEBGL`  
Compresses RGBA textures using explicit alpha encoding (useful when alpha transitions are sharp).

`ext.COMPRESSED_RGBA_ATC_INTERPOLATED_ALPHA_WEBGL`  
Compresses RGBA textures using interpolated alpha encoding (useful when alpha transitions are gradient).

Examples
--------

    var ext = gl.getExtension('WEBGL_compressed_texture_atc');

    var texture = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, texture);

    gl.compressedTexImage2D(gl.TEXTURE_2D, 0, ext.COMPRESSED_RGB_ATC_WEBGL, 512, 512, 0, textureData);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_compressed_texture_atc/">WEBGL_compressed_texture_atc<br />
<span class="small">The definition of 'WEBGL_compressed_texture_atc' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WEBGL_compressed_texture_atc`

No

No

18-64

Yes-58

No

No

No

37-68

36-68

?

24-48

No

3.0-10.0

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d)
-   [`WebGLRenderingContext.compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d)
-   [`WebGLRenderingContext.getParameter()`](webglrenderingcontext/getparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_atc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_atc</a>
