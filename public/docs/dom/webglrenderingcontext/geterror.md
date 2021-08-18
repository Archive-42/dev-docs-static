WebGLRenderingContext.getError()
================================

The `WebGLRenderingContext.getError()` method of the [WebGL API](../webgl_api) returns error information.

Syntax
------

    GLenum gl.getError();

### Parameters

None.

### Return value

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>gl.NO_ERROR</code></td><td>No error has been recorded. The value of this constant is 0.</td></tr><tr class="even"><td><code>gl.INVALID_ENUM</code></td><td>An unacceptable value has been specified for an enumerated argument. The command is ignored and the error flag is set.</td></tr><tr class="odd"><td><code>gl.INVALID_VALUE</code></td><td>A numeric argument is out of range. The command is ignored and the error flag is set.</td></tr><tr class="even"><td><code>gl.INVALID_OPERATION</code></td><td>The specified command is not allowed for the current state. The command is ignored and the error flag is set.</td></tr><tr class="odd"><td><code>gl.INVALID_FRAMEBUFFER_OPERATION</code></td><td>The currently bound framebuffer is not framebuffer complete when trying to render to or to read from it.</td></tr><tr class="even"><td><code>gl.OUT_OF_MEMORY</code></td><td>Not enough memory is left to execute the command.</td></tr><tr class="odd"><td><code>gl.CONTEXT_LOST_WEBGL</code></td><td>If the WebGL context is lost, this error is returned on the first call to <code>getError</code>. Afterwards and until the context has been restored, it returns <code>gl.NO_ERROR</code>.</td></tr></tbody></table>

Examples
--------

    gl.getError(); // gl.NO_ERROR (0)

    gl.enable(gl.FOOBAR);
    gl.getError(); // gl.INVALID_ENUM;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'getError' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetError.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetError' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`getError`

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

-   [`WebGLRenderingContext`](../webglrenderingcontext)
-   [`WebGLContextEvent`](../webglcontextevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getError</a>
