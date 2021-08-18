WebGL2RenderingContext.isTransformFeedback()
============================================

The `WebGL2RenderingContext.isTransformFeedback()` method of the [WebGL 2 API](../webgl_api) returns `true` if the passed object is a valid [`WebGLTransformFeedback`](../webgltransformfeedback) object.

Syntax
------

    GLboolean gl.isTransformFeedback(transformFeedback);

### Parameters

`transformFeedback`  
A [`WebGLTransformFeedback`](../webgltransformfeedback) object to test.

### Return value

A [`GLboolean`](../webgl_api/types) indicating whether the given object is a valid [`WebGLTransformFeedback`](../webgltransformfeedback) object (`true`) or not (`false`).

Examples
--------

`gl` must be a [`WebGL2RenderingContext`](../webgl2renderingcontext). `WebGLTransformFeedback` objects are not available in WebGL 1.

    var transformFeedback = gl.createTransformFeedback();

    // ...

    gl.isTransformFeedback(transformFeedback);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.15">WebGL 2.0<br />
<span class="small">The definition of 'isTransformFeedback' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glIsTransformFeedback.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glIsTransformFeedback' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`isTransformFeedback`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/isTransformFeedback" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/isTransformFeedback</a>
