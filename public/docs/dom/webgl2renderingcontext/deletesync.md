WebGL2RenderingContext.deleteSync()
===================================

The `WebGL2RenderingContext.deleteSync()` method of the [WebGL 2 API](../webgl_api) deletes a given [`WebGLSync`](../webglsync) object.

Syntax
------

    void gl.deleteSync(sync);

### Parameters

`sync`  
A [`WebGLSync`](../webglsync) object to delete.

### Return value

None.

Examples
--------

`gl` must be a [`WebGL2RenderingContext`](../webgl2renderingcontext). `WebGLSync` objects are not available in WebGL 1.

    var sync = gl.fenceSync(gl.SYNC_GPU_COMMANDS_COMPLETE, 0);

    // ...

    gl.deleteSync(sync);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.13">WebGL 2.0<br />
<span class="small">The definition of 'deleteSync' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glDeleteSync.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glDeleteSync' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`deleteSync`

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

-   [`WebGLSync`](../webglsync)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/deleteSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/deleteSync</a>
