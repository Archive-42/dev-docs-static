# EXT_texture_compression_bptc

The `EXT_texture_compression_bptc` extension is part of the [WebGL API](webgl_api) and exposes 4 BPTC compressed texture formats. These compression formats are called [BC7](https://docs.microsoft.com/en-us/windows/desktop/direct3d11/bc7-format) and [BC6H](https://docs.microsoft.com/en-us/windows/desktop/direct3d11/bc6h-format) in [Microsoft's DirectX API](https://docs.microsoft.com/en-us/windows/desktop/direct3d11/texture-block-compression-in-direct3d-11).

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** Support depends on the system's graphics driver. There is no support on Windows.

This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

## Constants

The compressed texture formats are exposed by 4 constants and can be used in two functions: [`compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d) and [`compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d).

`ext.COMPRESSED_RGBA_BPTC_UNORM_EXT`  
Compresses 8-bit fixed-point data. Each 4x4 block of texels consists of 128 bits of RGBA or image data. See also [BC7 format](https://docs.microsoft.com/en-us/windows/desktop/direct3d11/bc7-format).

`ext.COMPRESSED_SRGB_ALPHA_BPTC_UNORM_EXT`  
Compresses 8-bit fixed-point data. Each 4x4 block of texels consists of 128 bits of SRGB_ALPHA or image data. See also [BC7 format](https://docs.microsoft.com/en-us/windows/desktop/direct3d11/bc7-format).

`ext.COMPRESSED_RGB_BPTC_SIGNED_FLOAT_EXT`  
Compresses high dynamic range signed floating point values. Each 4x4 block of texels consists of 128 bits of RGB data. It only contains RGB data, so the returned alpha value is 1.0. See also [BC6H format](https://docs.microsoft.com/en-us/windows/desktop/direct3d11/bc6h-format).

`ext.COMPRESSED_RGB_BPTC_UNSIGNED_FLOAT_EXT`  
Compresses high dynamic range unsigned floating point values. Each 4x4 block of texels consists of 128 bits of RGB data. It only contains RGB data, so the returned alpha value is 1.0. See also [BC6H format](https://docs.microsoft.com/en-us/windows/desktop/direct3d11/bc6h-format).

## Examples

    var ext = gl.getExtension('EXT_texture_compression_bptc');

    var texture = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, texture);

    gl.compressedTexImage2D(gl.TEXTURE_2D, 0, ext.COMPRESSED_RGBA_BPTC_UNORM_EXT, 128, 128, 0, textureData);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_texture_compression_bptc/">EXT_texture_compression_bptc</a></td><td>Community Approved</td></tr></tbody></table>

## Browser compatibility

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

`EXT_texture_compression_bptc`

No

No

68

No

No

No

No

No

No

No

No

No

## See also

- [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
- [`WebGLRenderingContext.compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d)
- [`WebGLRenderingContext.compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d)
- [`WebGLRenderingContext.getParameter()`](webglrenderingcontext/getparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_texture_compression_bptc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_texture_compression_bptc</a>
