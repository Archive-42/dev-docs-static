WebGL2RenderingContext.bindBufferRange()
========================================

The `WebGL2RenderingContext.bindBufferRange()` method of the [WebGL 2 API](../webgl_api) binds a range of a given [`WebGLBuffer`](../webglbuffer) to a given binding point (`target`) at a given `index`.

Syntax
------

    void gl.bindBufferRange(target, index, buffer, offset, size);

### Parameters

`target`  
A [`Glenum`](../webgl_api/types) specifying the target for the bind operation. Possible values:

-   `gl.TRANSFORM_FEEDBACK_BUFFER`
-   `gl.UNIFORM_BUFFER`

`index`  
A [`GLuint`](../webgl_api/types) specifying the index of the `target`.

`buffer`  
A [`WebGLBuffer`](../webglbuffer) which to bind to the binding point (`target`).

offset  
A [`GLintptr`](../webgl_api/types) specifying the starting offset.

size  
A [`GLsizeiptr`](../webgl_api/types) specifying the amount of data that can be read from the buffer.

### Return value

None.

Examples
--------

    gl.bindBufferRange(gl.TRANSFORM_FEEDBACK_BUFFER, 1, buffer, 0, 4);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.16">WebGL 2.0<br />
<span class="small">The definition of 'bindBufferRange' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBindBufferRange.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBindBufferRange' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`bindBufferRange`

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

-   [`WebGL2RenderingContext.bindBufferBase()`](bindbufferbase)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/bindBufferRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/bindBufferRange</a>
