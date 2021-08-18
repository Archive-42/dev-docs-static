WebGL2RenderingContext.transformFeedbackVaryings()
==================================================

The `WebGL2RenderingContext.transformFeedbackVaryings()` method of the [WebGL 2 API](../webgl_api) specifies values to record in [`WebGLTransformFeedback`](../webgltransformfeedback) buffers.

Syntax
------

    void gl.transformFeedbackVaryings(program, varyings, bufferMode);

### Parameters

program  
A [`WebGLProgram`](../webglprogram).

varyings  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`DOMString`](../domstring) specifying the names of the varying variables to use.

`bufferMode`  
A [`GLenum`](../webgl_api/types) specifying the mode to use when capturing the varying variables. Either `gl.INTERLEAVED_ATTRIBS` or `gl.SEPARATE_ATTRIBS`.

### Return value

None.

Examples
--------

    var transformFeedback = gl.createTransformFeedback();
    gl.bindTransformFeedback(gl.TRANSFORM_FEEDBACK, transformFeedback);
    var transformFeedbackOutputs = ['gl_Position', 'anotherOutput'];

    gl.transformFeedbackVaryings(shaderProg, transformFeedbackOutputs,
                                 gl.INTERLEAVED_ATTRIBS);
    gl.linkProgram(shaderProg);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.15">WebGL 2.0<br />
<span class="small">The definition of 'transformFeedbackVaryings' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glTransformFeedbackVaryings.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glTransformFeedbackVaryings' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`transformFeedbackVaryings`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/transformFeedbackVaryings" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/transformFeedbackVaryings</a>
