WebGL2RenderingContext.beginTransformFeedback()
===============================================

The `WebGL2RenderingContext.beginTransformFeedback()` method of the [WebGL 2 API](../webgl_api) starts a transform feedback operation.

Syntax
------

    void gl.beginTransformFeedback(primitiveMode);

### Parameters

`primitiveMode`  
A [`GLenum`](../webgl_api/types) specifying the output type of the primitives that will be recorded into the buffer objects that are bound for transform feedback. Possible values:

-   `gl.POINTS`
-   `gl.LINES`
-   `gl.TRIANGLES`

### Return value

None.

Examples
--------

    var transformFeedback = gl.createTransformFeedback();
    gl.bindTransformFeedback(gl.TRANSFORM_FEEDBACK, transformFeedback);
    gl.beginTransformFeedback(gl.TRIANGLES);
    gl.drawArrays(gl.TRIANGLES, 0, 3);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.15">WebGL 2.0<br />
<span class="small">The definition of 'beginTransformFeedback' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBeginTransformFeedback.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBeginTransformFeedback' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`beginTransformFeedback`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/beginTransformFeedback" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/beginTransformFeedback</a>
