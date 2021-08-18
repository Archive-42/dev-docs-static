WebGLRenderingContext.finish()
==============================

The `WebGLRenderingContext.finish()` method of the [WebGL API](../webgl_api) blocks execution until all previously called commands are finished.

Syntax
------

    void gl.finish();

### Parameters

None.

### Return value

None.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.11">WebGL 1.0<br />
<span class="small">The definition of 'finish' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glFinish.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glFinish' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`finish`

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

-   [`WebGLRenderingContext.flush()`](flush)
-   [WebGL best practices](../webgl_api/webgl_best_practices) (which recommends avoiding `finish()` as it may slow down your main rendering loop)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/finish" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/finish</a>
