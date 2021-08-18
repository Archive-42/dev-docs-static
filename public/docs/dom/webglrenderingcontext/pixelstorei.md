WebGLRenderingContext.pixelStorei()
===================================

The `WebGLRenderingContext.pixelStorei()` method of the [WebGL API](../webgl_api) specifies the pixel storage modes.

Syntax
------

    void gl.pixelStorei(pname, param);

### Parameters

pname  
A [`Glenum`](../webgl_api/types) specifying which parameter to set. See below for possible values.

param  
A [`GLint`](../webgl_api/types) specifying a value to set the *`pname`* parameter to. See below for possible values.

### Return value

None.

Pixel storage parameters
------------------------

<table><thead><tr class="header"><th>Parameter name (for <code>pname</code>)</th><th>Description</th><th>Type</th><th>Default value</th><th>Allowed values (for <code>param</code>)</th><th>Specified in</th></tr></thead><tbody><tr class="odd"><td><code>gl.PACK_ALIGNMENT</code></td><td>Packing of pixel data into memory</td><td><a href="../webgl_api/types"><code>GLint</code></a></td><td>4</td><td>1, 2, 4, 8</td><td>OpenGL ES 2.0</td></tr><tr class="even"><td><code>gl.UNPACK_ALIGNMENT</code></td><td>Unpacking of pixel data from memory.</td><td><a href="../webgl_api/types"><code>GLint</code></a></td><td>4</td><td>1, 2, 4, 8</td><td>OpenGL ES 2.0</td></tr><tr class="odd"><td><code>gl.UNPACK_FLIP_Y_WEBGL</code></td><td>Flips the source data along its vertical axis if true.</td><td><a href="../webgl_api/types"><code>GLboolean</code></a></td><td>false</td><td>true, false</td><td>WebGL</td></tr><tr class="even"><td><code>gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL</code></td><td>Multiplies the alpha channel into the other color channels</td><td><a href="../webgl_api/types"><code>GLboolean</code></a></td><td>false</td><td>true, false</td><td>WebGL</td></tr><tr class="odd"><td><code>gl.UNPACK_COLORSPACE_CONVERSION_WEBGL</code></td><td>Default color space conversion or no color space conversion.</td><td><a href="../webgl_api/types"><code>GLenum</code></a></td><td><code>gl.BROWSER_DEFAULT_WEBGL</code></td><td><code>gl.BROWSER_DEFAULT_WEBGL</code>, <code>gl.NONE</code></td><td>WebGL</td></tr></tbody></table>

When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:

<table><thead><tr class="header"><th>Constant</th><th>Description</th><th>Type</th><th>Default value</th><th>Allowed values (for <code>param</code>)</th><th>Specified in</th></tr></thead><tbody><tr class="odd"><td><code>gl.PACK_ROW_LENGTH</code></td><td>Number of pixels in a row.</td><td><a href="../webgl_api/types"><code>GLint</code></a></td><td>0</td><td>0 to <code>Infinity</code></td><td>OpenGL ES 3.0</td></tr><tr class="even"><td><code>gl.PACK_SKIP_PIXELS</code></td><td>Number of pixel locations skipped before the first pixel is written into memory.</td><td><a href="../webgl_api/types"><code>GLint</code></a></td><td>0</td><td>0 to <code>Infinity</code></td><td>OpenGL ES 3.0</td></tr><tr class="odd"><td><code>gl.PACK_SKIP_ROWS</code></td><td>Number of rows of pixel locations skipped before the first pixel is written into memory</td><td><a href="../webgl_api/types"><code>GLint</code></a></td><td>0</td><td>0 to <code>Infinity</code></td><td>OpenGL ES 3.0</td></tr><tr class="even"><td><code>gl.UNPACK_ROW_LENGTH</code></td><td>Number of pixels in a row.</td><td><a href="../webgl_api/types"><code>GLint</code></a></td><td>0</td><td>0 to <code>Infinity</code></td><td>OpenGL ES 3.0</td></tr><tr class="odd"><td><code>gl.UNPACK_IMAGE_HEIGHT</code></td><td>Image height used for reading pixel data from memory</td><td><a href="../webgl_api/types"><code>GLint</code></a></td><td>0</td><td>0 to <code>Infinity</code></td><td>OpenGL ES 3.0</td></tr><tr class="even"><td><code>gl.UNPACK_SKIP_PIXELS</code></td><td>Number of pixel images skipped before the first pixel is read from memory</td><td><a href="../webgl_api/types"><code>GLint</code></a></td><td>0</td><td>0 to <code>Infinity</code></td><td>OpenGL ES 3.0</td></tr><tr class="odd"><td><code>gl.UNPACK_SKIP_ROWS</code></td><td>Number of rows of pixel locations skipped before the first pixel is read from memory</td><td><a href="../webgl_api/types"><code>GLint</code></a></td><td>0</td><td>0 to <code>Infinity</code></td><td>OpenGL ES 3.0</td></tr><tr class="even"><td><code>gl.UNPACK_SKIP_IMAGES</code></td><td>Number of pixel images skipped before the first pixel is read from memory</td><td><a href="../webgl_api/types"><code>GLint</code></a></td><td>0</td><td>0 to <code>Infinity</code></td><td>OpenGL ES 3.0</td></tr></tbody></table>

Examples
--------

Setting the pixel storage mode affects the [`WebGLRenderingContext.readPixels()`](readpixels) operations, as well as unpacking of textures with the [`WebGLRenderingContext.texImage2D()`](teximage2d) and [`WebGLRenderingContext.texSubImage2D()`](texsubimage2d) methods.  

    var tex = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D, tex);
    gl.pixelStorei(gl.PACK_ALIGNMENT, 4);

To check the values for packing and unpacking of pixel data, you can query the same pixel storage parameters with [`WebGLRenderingContext.getParameter()`](getparameter).

    gl.getParameter(gl.PACK_ALIGNMENT);
    gl.getParameter(gl.UNPACK_ALIGNMENT);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'pixelStorei' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#PIXEL_STORAGE_PARAMETERS">WebGL 1.0<br />
<span class="small">The definition of 'Pixel Storage Parameters' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Additional pixel storage parameters that aren't specified in OpenGL.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glPixelStorei.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glPixelStorei' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL ES 2.0 API.</td></tr><tr class="even"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.2">WebGL 2.0<br />
<span class="small">The definition of 'pixelStorei' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL 2.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glPixelStorei.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glPixelStorei' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`pixelStorei`

9

12

4

11

12

5.1

≤37

25

Yes

12

8

1.5

`WebGL2`

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

-   [`WebGLRenderingContext.readPixels()`](readpixels)
-   [`WebGLRenderingContext.texImage2D()`](teximage2d)
-   [`WebGLRenderingContext.texSubImage2D()`](texsubimage2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/pixelStorei" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/pixelStorei</a>
