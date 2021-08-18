WebGL2RenderingContext.getIndexedParameter()
============================================

The `WebGL2RenderingContext.getIndexedParameter()` method of the [WebGL 2 API](../webgl_api) returns indexed information about a given `target`.

Syntax
------

    any gl.getIndexedParameter(target, index);

### Parameters

`target`  
A [`Glenum`](../webgl_api/types) specifying the target for which to return information. Possible values:

-   `gl.TRANSFORM_FEEDBACK_BUFFER_BINDING`: Returns a [`WebGLBuffer`](../webglbuffer).
-   `gl.TRANSFORM_FEEDBACK_BUFFER_SIZE`: Returns a [`GLsizeiptr`](../webgl_api/types).
-   `gl.TRANSFORM_FEEDBACK_BUFFER_START`: Returns a [`GLintptr`](../webgl_api/types).
-   `gl.UNIFORM_BUFFER_BINDING`: Returns a [`WebGLBuffer`](../webglbuffer).
-   `gl.UNIFORM_BUFFER_SIZE`: Returns a [`GLsizeiptr`](../webgl_api/types).
-   `gl.UNIFORM_BUFFER_START`: Returns a [`GLintptr`](../webgl_api/types).

`index`  
A [`GLuint`](../webgl_api/types) specifying the index of the `target` that is queried.

### Return value

Depends on the requested information (as specified with `target`).

Examples
--------

    var binding = gl.getIndexedParameter(gl.TRANSFORM_FEEDBACK_BUFFER_BINDING, 0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.2">WebGL 2.0<br />
<span class="small">The definition of 'getIndexedParameter' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGet.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGet' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getIndexedParameter`

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

-   [`WebGLRenderingContext.getParameter()`](../webglrenderingcontext/getparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getIndexedParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getIndexedParameter</a>
