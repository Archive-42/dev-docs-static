WebGL2RenderingContext.getTransformFeedbackVarying()
====================================================

The `WebGL2RenderingContext.getTransformFeedbackVarying()` method of the [WebGL 2 API](../webgl_api) returns information about varying variables from [`WebGLTransformFeedback`](../webgltransformfeedback) buffers.

Syntax
------

    WebGLActiveInfo gl.getTransformFeedbackVarying(program, index);

### Parameters

program  
A [`WebGLProgram`](../webglprogram).

index  
A [`GLuint`](../webgl_api/types) specifying the index of the varying variable whose information to retrieve`.`

### Return value

A [`WebGLActiveInfo`](../webglactiveinfo) object.

Examples
--------

    activeInfo = gl.getTransformFeedbackVarying(program, 0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.15">WebGL 2.0<br />
<span class="small">The definition of 'getTransformFeedbackVarying' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetTransformFeedbackVarying.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetTransformFeedbackVarying' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getTransformFeedbackVarying`

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

-   [`WebGLTransformFeedback`](../webgltransformfeedback)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getTransformFeedbackVarying" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getTransformFeedbackVarying</a>
