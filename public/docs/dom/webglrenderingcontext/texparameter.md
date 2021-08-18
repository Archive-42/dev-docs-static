WebGLRenderingContext.texParameter\[fi\]()
==========================================

The `WebGLRenderingContext.texParameter[fi]()` methods of the [WebGL API](../webgl_api) set texture parameters.

Syntax
------

    void gl.texParameterf(GLenum target, GLenum pname, GLfloat param);
    void gl.texParameteri(GLenum target, GLenum pname, GLint param);

### Parameters

target  
A [`GLenum`](../webgl_api/types) specifying the binding point (target). Possible values:

-   `gl.TEXTURE_2D`: A two-dimensional texture.
-   `gl.TEXTURE_CUBE_MAP`: A cube-mapped texture.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.TEXTURE_3D`: A three-dimensional texture.
    -   `gl.TEXTURE_2D_ARRAY`: A two-dimensional array texture.

The `pname` parameter is a [`Glenum`](../webgl_api/types) specifying the texture parameter to set. The `param` parameter is a [`GLfloat`](../webgl_api/types) or [`GLint`](../webgl_api/types) specifying the value for the specified parameter `pname`.

`pname`

Description

`param`

Available in WebGL 1

`gl.TEXTURE_MAG_FILTER`

Texture magnification filter

`gl.LINEAR` (default value), `gl.NEAREST`.

`gl.TEXTURE_MIN_FILTER`

Texture minification filter

`gl.LINEAR`, `gl.NEAREST`, `gl.NEAREST_MIPMAP_NEAREST`, `gl.LINEAR_MIPMAP_NEAREST`, `gl.NEAREST_MIPMAP_LINEAR` (default value), `gl.LINEAR_MIPMAP_LINEAR`.

`gl.TEXTURE_WRAP_S`

Wrapping function for texture coordinate `s`

`gl.REPEAT` (default value),`gl.CLAMP_TO_EDGE`, `gl.MIRRORED_REPEAT`.

`gl.TEXTURE_WRAP_T`

Wrapping function for texture coordinate `t`

`gl.REPEAT` (default value),`gl.CLAMP_TO_EDGE`, `gl.MIRRORED_REPEAT`.

Additionally available when using the [`EXT_texture_filter_anisotropic`](../ext_texture_filter_anisotropic) extension

`ext.TEXTURE_MAX_ANISOTROPY_EXT`

Maximum anisotropy for a texture

A [`GLfloat`](../webgl_api/types) value.

Additionally available when using a WebGL 2 context

`gl.TEXTURE_BASE_LEVEL`

Texture mipmap level

Any int values.

`gl.TEXTURE_COMPARE_FUNC`

Texture Comparison function

`gl.LEQUAL` (default value), `gl.GEQUAL`, `gl.LESS`, `gl.GREATER`, `gl.EQUAL`, `gl.NOTEQUAL`, `gl.ALWAYS`, `gl.NEVER`.

`gl.TEXTURE_COMPARE_MODE`

Texture comparison mode

`gl.NONE` (default value), `gl.COMPARE_REF_TO_TEXTURE`.

`gl.TEXTURE_MAX_LEVEL`

Maximum texture mipmap array level

Any int values.

`gl.TEXTURE_MAX_LOD`

Texture maximum level-of-detail value

Any float values.

`gl.TEXTURE_MIN_LOD`

Texture minimum level-of-detail value

Any float values.

`gl.TEXTURE_WRAP_R`

Wrapping function for texture coordinate `r`

`gl.REPEAT` (default value), `gl.CLAMP_TO_EDGE`, `gl.MIRRORED_REPEAT`.

### Return value

None.

Examples
--------

    gl.texParameterf(gl.TEXTURE_2D, gl.TEXTURE_MAG_FILTER, gl.LINEAR);
    gl.texParameteri(gl.TEXTURE_2D, gl.TEXTURE_MIN_FILTER, gl.LINEAR_MIPMAP_NEAREST);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.8">WebGL 1.0<br />
<span class="small">The definition of 'texParameter[fi]' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glTexParameter.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glTexParameter' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2.0 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.6">WebGL 2.0<br />
<span class="small">The definition of 'texParameter[fi]' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glTexParameter.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glTexParameter' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`texParameter`

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

`texParameter`

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

BCD tables only load in the browser

### WebGLRenderingContext.texParameteri()

BCD tables only load in the browser

See also
--------

-   [`WebGLRenderingContext.getTexParameter()`](gettexparameter)
-   [`EXT_texture_filter_anisotropic`](../ext_texture_filter_anisotropic)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/texParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/texParameter</a>
