WebGLRenderingContext.shaderSource()
====================================

The `WebGLRenderingContext.shaderSource()` method of the [WebGL API](../webgl_api) sets the source code of a [`WebGLShader`](../webglshader).

Syntax
------

    void gl.shaderSource(shader, source);

### Parameters

shader  
A [`WebGLShader`](../webglshader) object in which to set the source code.

source  
A [`DOMString`](../domstring) containing the GLSL source code to set.

### Return value

None.

Examples
--------

    var shader = gl.createShader(gl.VERTEX_SHADER);
    gl.shaderSource(shader, originalSource);

    var source = gl.getShaderSource(shader);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'shaderSource' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glShaderSource.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glShaderSource' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`shaderSource`

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

-   [`WebGLRenderingContext.createShader()`](createshader)
-   [`WebGLRenderingContext.isShader()`](isshader)
-   [`WebGLRenderingContext.deleteShader()`](deleteshader)
-   [`WebGLRenderingContext.getShaderSource()`](getshadersource)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/shaderSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/shaderSource</a>
