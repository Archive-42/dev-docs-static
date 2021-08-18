WebGLRenderingContext.getShaderInfoLog()
========================================

The **WebGLRenderingContext.getShaderInfoLog** returns the information log for the specified [`WebGLShader`](../webglshader) object. It contains warnings, debugging and compile information.

Syntax
------

    gl.getShaderInfoLog(shader);

### Parameters

shader  
A [`WebGLShader`](../webglshader) to query.

### Return value

A [`DOMString`](../domstring) that contains diagnostic messages, warning messages, and other information about the last compile operation. When a [`WebGLShader`](../webglshader) object is initially created, its information log will be a string of length 0.

Examples
--------

### Checking compilation messages

    /* load shader source code. */
    gl.shaderSource(shader, shaderCode);

    /* compile shader source code. */
    gl.compileShader(shader);

    var message = gl.getShaderInfoLog(shader);

    if (message.length > 0) {
      /* message may be an error or a warning */
      throw message;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'getShaderInfoLog' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetShaderInfoLog.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetShaderInfoLog' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`getShaderInfoLog`

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

-   [`WebGLRenderingContext.getShaderParameter()`](getshaderparameter) – used with `gl.COMPILE_STATUS` to check for a failed compile.
-   [`WebGLRenderingContext.getError()`](geterror)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getShaderInfoLog" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getShaderInfoLog</a>
