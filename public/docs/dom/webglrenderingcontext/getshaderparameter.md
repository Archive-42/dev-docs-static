WebGLRenderingContext.getShaderParameter()
==========================================

The `WebGLRenderingContext.getShaderParameter()` method of the [WebGL API](../webgl_api) returns information about the given shader.

Syntax
------

    any gl.getShaderParameter(shader, pname);

### Parameters

shader  
A [`WebGLShader`](../webglshader) to get parameter information from.

pname  
A [`GLenum`](../webgl_api/types) specifying the information to query. Possible values:

-   `gl.DELETE_STATUS`: Returns a [`GLboolean`](../webgl_api/types) indicating whether or not the shader is flagged for deletion.
-   `gl.COMPILE_STATUS`: Returns a [`GLboolean`](../webgl_api/types) indicating whether or not the last shader compilation was successful.
-   `gl.SHADER_TYPE`: Returns a [`GLenum`](../webgl_api/types) indicating whether the shader is a vertex shader (`gl.VERTEX_SHADER`) or fragment shader (`gl.FRAGMENT_SHADER`) object.

### Return value

Returns the requested shader information (as specified with `pname`).

Examples
--------

    gl.getShaderParameter(shader, gl.SHADER_TYPE);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'getShaderParameter' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetShaderiv.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetShaderiv' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getShaderParameter`

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

-   [`WebGLRenderingContext.getProgramParameter()`](getprogramparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getShaderParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getShaderParameter</a>
