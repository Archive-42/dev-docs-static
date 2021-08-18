WebGLRenderingContext.uniform\[1234\]\[fi\]\[v\]()
==================================================

The `WebGLRenderingContext.uniform[1234][fi][v]()` methods of the [WebGL API](../webgl_api) specify values of uniform variables. All active uniform variables defined in a program object are initialized to 0 when the program object is linked successfully. They retain the values assigned to them by a call to this method until the next successful link operation occurs on the program object, when they are once again initialized to 0.

Many of the functions described here have expanded WebGL 2 interfaces, which can be found under [`WebGL2RenderingContext.uniform[1234][uif][v]()`](../webgl2renderingcontext/uniform).

Syntax
------

    void gl.uniform1f(location, v0);
    void gl.uniform1fv(location, value);
    void gl.uniform1i(location, v0);
    void gl.uniform1iv(location, value);

    void gl.uniform2f(location, v0, v1);
    void gl.uniform2fv(location, value);
    void gl.uniform2i(location, v0, v1);
    void gl.uniform2iv(location, value);

    void gl.uniform3f(location, v0, v1, v2);
    void gl.uniform3fv(location, value);
    void gl.uniform3i(location, v0, v1, v2);
    void gl.uniform3iv(location, value);

    void gl.uniform4f(location, v0, v1, v2, v3);
    void gl.uniform4fv(location, value);
    void gl.uniform4i(location, v0, v1, v2, v3);
    void gl.uniform4iv(location, value);

### Parameters

location  
A [`WebGLUniformLocation`](../webgluniformlocation) object containing the location of the uniform attribute to modify.

`value, v0, v1, v2, v3`  
A new value to be used for the uniform variable. Possible types:

-   A floating point [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) for floating point values (methods with "f").
-   A sequence of floating point numbers (for example a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) or an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of numbers) for floating point vector methods (methods with "fv").
-   An integer [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) for integer values (methods with "i").
-   An [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array) for integer vector methods (methods with "iv").

### Return value

None.

Examples
--------

    gl.uniform1f(u_alpha, 0.8);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.10">WebGL 1.0<br />
<span class="small">The definition of 'uniform' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glUniform.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glUniform' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Main page of the OpenGL API.</td></tr></tbody></table>

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

See also
--------

-   [`WebGLRenderingContext.uniformMatrix()`](uniformmatrix)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/uniform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/uniform</a>
