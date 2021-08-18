WebGL2RenderingContext.bindTransformFeedback()
==============================================

The `WebGL2RenderingContext.bindTransformFeedback()` method of the [WebGL 2 API](../webgl_api) binds a passed [`WebGLTransformFeedback`](../webgltransformfeedback) object to the current GL state.

Syntax
------

    void gl.bindTransformFeedback(target, transformFeedback);

### Parameters

`target`  
A [`GLenum`](../webgl_api/types) specifying the target (binding point). Must be `gl.TRANSFORM_FEEDBACK`.

`transformFeedback`  
A [`WebGLTransformFeedback`](../webgltransformfeedback) object to bind.

### Return value

None.

Examples
--------

    var transformFeedback = gl.createTransformFeedback();
    gl.bindTransformFeedback(gl.TRANSFORM_FEEDBACK, transformFeedback);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.15">WebGL 2.0<br />
<span class="small">The definition of 'bindTransformFeedback' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBindTransformFeedback.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBindTransformFeedback' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`bindTransformFeedback`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/bindTransformFeedback" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/bindTransformFeedback</a>
