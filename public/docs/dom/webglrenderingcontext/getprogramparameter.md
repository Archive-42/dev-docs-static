WebGLRenderingContext.getProgramParameter()
===========================================

The `WebGLRenderingContext.getProgramParameter()` method of the [WebGL API](../webgl_api) returns information about the given program.

Syntax
------

    any gl.getProgramParameter(program, pname);

### Parameters

program  
A [`WebGLProgram`](../webglprogram) to get parameter information from.

pname  
A [`Glenum`](../webgl_api/types) specifying the information to query. Possible values:

-   `gl.DELETE_STATUS`: Returns a [`GLboolean`](../webgl_api/types) indicating whether or not the program is flagged for deletion.
-   `gl.LINK_STATUS`: Returns a [`GLboolean`](../webgl_api/types) indicating whether or not the last link operation was successful.
-   `gl.VALIDATE_STATUS`: Returns a [`GLboolean`](../webgl_api/types) indicating whether or not the last validation operation was successful.
-   `gl.ATTACHED_SHADERS`: Returns a [`GLint`](../webgl_api/types) indicating the number of attached shaders to a program.
-   `gl.ACTIVE_ATTRIBUTES`: Returns a [`GLint`](../webgl_api/types) indicating the number of active attribute variables to a program.
-   `gl.ACTIVE_UNIFORMS`: Returns a [`GLint`](../webgl_api/types) indicating the number of active uniform variables to a program.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.TRANSFORM_FEEDBACK_BUFFER_MODE`: Returns a [`GLenum`](../webgl_api/types) indicating the buffer mode when transform feedback is active. May be `gl.SEPARATE_ATTRIBS` or `gl.INTERLEAVED_ATTRIBS`.
    -   `gl.TRANSFORM_FEEDBACK_VARYINGS`: Returns a [`GLint`](../webgl_api/types) indicating the number of varying variables to capture in transform feedback mode.
    -   `gl.ACTIVE_UNIFORM_BLOCKS`: Returns a [`GLint`](../webgl_api/types) indicating the number of uniform blocks containing active uniforms.

### Return value

Returns the requested program information (as specified with `pname`).

Examples
--------

    gl.getProgramParameter(program, gl.DELETE_STATUS);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'getProgramParameter' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetProgramiv.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetProgramiv' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.7">WebGL 2.0<br />
<span class="small">The definition of 'getProgramParameter' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds new <code>pname</code> values:<br />
<code>gl.TRANSFORM_FEEDBACK_BUFFER_MODE</code>,<br />
<code>gl.TRANSFORM_FEEDBACK_VARYINGS</code>,<br />
<code>gl.ACTIVE_UNIFORM_BLOCKS</code></td></tr></tbody></table>

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

`getProgramParameter`

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

-   [`WebGLRenderingContext.getShaderParameter()`](getshaderparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getProgramParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getProgramParameter</a>
