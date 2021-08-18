WebGL2RenderingContext.texStorage2D()
=====================================

The `WebGL2RenderingContext.texStorage2D()` method of the [WebGL API](../webgl_api) specifies all levels of two-dimensional texture storage.

Syntax
------

    void gl.texStorage2D(target, levels, internalformat, width, height);

### Parameters

`target`  
A [`GLenum`](../webgl_api/types) specifying the binding point (target) of the active texture. Possible values:

-   `gl.TEXTURE_2D`: A two-dimensional texture.
-   `gl.TEXTURE_CUBE_MAP`: A cube-mapped texture.

`levels`  
A [`GLint`](../webgl_api/types) specifying the number of texture levels.

`internalformat`  
A [`GLenum`](../webgl_api/types) specifying the texture store format. Possible values:

-   `gl.R8`
-   `gl.R16F`
-   `gl.R32F`
-   `gl.R8UI`
-   `gl.RG8`
-   `gl.RG16F`
-   `gl.RG32F`
-   `gl.RG8UI`
-   `gl.RGB8`
-   `gl.SRGB8`
-   `gl.RGB565`
-   `gl.R11F_G11F_B10F`
-   `gl.RGB9_E5`
-   `gl.RGB16F`
-   `gl.RGB32F`
-   `gl.RGB8UI`
-   `gl.RGBA8`
-   `gl.SRGB8_APLHA8`
-   `gl.RGB5_A1`
-   `gl.RGBA4`
-   `gl.RGBA16F`
-   `gl.RGBA32F`
-   `gl.RGBA8UI`

Unlike OpenGL 3.0, WebGL 2 **doesn't support** the following ETC2 and EAC compressed texture formats (see [section 5.37](https://www.khronos.org/registry/webgl/specs/latest/2.0/#5.37) in the WebGL 2 spec). You might be able to enable them via the [`WEBGL_compressed_texture_etc`](../webgl_compressed_texture_etc) extension, though.

-   `gl.COMPRESSED_R11_EAC`
-   `gl.COMPRESSED_SIGNED_R11_EAC`
-   `gl.COMPRESSED_RG11_EAC`
-   `gl.COMPRESSED_SIGNED_RG11_EAC`
-   `gl.COMPRESSED_RGB8_ETC2`
-   `gl.COMPRESSED_RGBA8_ETC2_EAC`
-   `gl.COMPRESSED_SRGB8_ETC2`
-   `gl.COMPRESSED_SRGB8_ALPHA8_ETC2_EAC`
-   `gl.COMPRESSED_RGB8_PUNCHTHROUGH_ALPHA1_ETC2`
-   `gl.COMPRESSED_SRGB8_PUNCHTHROUGH_ALPHA1_ETC2`

`width`  
A [`GLsizei`](../webgl_api/types) specifying the width of the texture.

`height`  
A [`GLsizei`](../webgl_api/types) specifying the height of the texture.

### Return value

None.

Examples
--------

    gl.texStorage2D(gl.TEXTURE_2D, 1, gl.RGB8, 256, 256);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.6">WebGL 2.0<br />
<span class="small">The definition of 'texStorage2D' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glTexStorage2D.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glTexStorage2D' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`texStorage2D`

56

79

51

No

43

No

58

58

51

43

No

7.0

See also
--------

-   [`WebGL2RenderingContext.texStorage3D()`](texstorage3d)
-   [`WEBGL_compressed_texture_etc`](../webgl_compressed_texture_etc)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/texStorage2D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/texStorage2D</a>
