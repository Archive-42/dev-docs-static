WebGL2RenderingContext.uniform\[1234\]\[uif\]\[v\]()
====================================================

The `WebGL2RenderingContext.uniform[1234][uif][v]()` methods of the [WebGL API](../webgl_api) specify values of uniform variables.

`ui` stands for *unsigned integer*, `i` for *integer,* `f` for *float*, and `v` for *vector.*  
Not all combinations are valid: `u` cannot be combined with `f`. See the syntax table below. Equivalent Regex: `uniform[1234](u?i|f)v?`

Syntax
------

    void gl.uniform1ui(location, v0);
    void gl.uniform2ui(location, v0, v1);
    void gl.uniform3ui(location, v0, v1, v2);
    void gl.uniform4ui(location, v0, v1, v2, v3);
    void gl.uniform1fv(location, data, optional srcOffset, optional srcLength);
    void gl.uniform2fv(location, data, optional srcOffset, optional srcLength);
    void gl.uniform3fv(location, data, optional srcOffset, optional srcLength);
    void gl.uniform4fv(location, data, optional srcOffset, optional srcLength);
    void gl.uniform1iv(location, data, optional srcOffset, optional srcLength);
    void gl.uniform2iv(location, data, optional srcOffset, optional srcLength);
    void gl.uniform3iv(location, data, optional srcOffset, optional srcLength);
    void gl.uniform4iv(location, data, optional srcOffset, optional srcLength);
    void gl.uniform1uiv(location, data, optional srcOffset, optional srcLength);
    void gl.uniform2uiv(location, data, optional srcOffset, optional srcLength);
    void gl.uniform3uiv(location, data, optional srcOffset, optional srcLength);
    void gl.uniform4uiv(location, data, optional srcOffset, optional srcLength);

### Parameters

location  
A [`WebGLUniformLocation`](../webgluniformlocation) object containing the location of the uniform attribute to modify.

`data, v0, v1, v2, v3`  
A new value to be used for the uniform variable. Possible types:

-   A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) for unsigned integer values (methods with `ui`), for integer values (methods with `i`), or for floats (methods with `f`).
-   A [`Uint32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array) for unsigned integer vector methods (methods with `uiv`).

### Return value

None.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.8">WebGL 2.0<br />
<span class="small">The definition of 'uniform' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glUniform.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glUniform' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`uniform`

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

-   [`WebGLRenderingContext.uniform()`](../webglrenderingcontext/uniform)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/uniform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/uniform</a>
