WebGLRenderingContext.getTexParameter()
=======================================

The `WebGLRenderingContext.getTexParameter()` method of the [WebGL API](../webgl_api) returns information about the given texture.

Syntax
------

    any gl.getTexParameter(target, pname);

### Parameters

target  
A [`GLenum`](../webgl_api/types) specifying the binding point (target). Possible values:

-   `gl.TEXTURE_2D`: A two-dimensional texture.
-   `gl.TEXTURE_CUBE_MAP`: A cube-mapped texture.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.TEXTURE_3D`: A three-dimensional texture.
    -   `gl.TEXTURE_2D_ARRAY`: A two-dimensional array texture.

pname  
A [`Glenum`](../webgl_api/types) specifying the information to query. Possible values:

pname

### Return value

Returns the requested texture information (as specified with `pname`). If an error occurs, [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) is returned.

Examples
--------

    gl.getTexParameter(gl.TEXTURE_2D, gl.TEXTURE_MAG_FILTER);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.8">WebGL 1.0<br />
<span class="small">The definition of 'getTexParameter' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetTexParameter.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetTexParameter' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2.0 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.6">WebGL 2.0<br />
<span class="small">The definition of 'getTexParameter' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetTexParameter.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetTexParameter' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`getTexParameter`

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

-   [`WebGLRenderingContext.texParameterf()`](texparameter)
-   [`WebGLRenderingContext.texParameteri()`](texparameter)
-   [`EXT_texture_filter_anisotropic`](../ext_texture_filter_anisotropic)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getTexParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getTexParameter</a>
