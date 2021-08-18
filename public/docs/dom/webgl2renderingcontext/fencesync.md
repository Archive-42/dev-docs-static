WebGL2RenderingContext.fenceSync()
==================================

The `WebGL2RenderingContext.fenceSync()` method of the [WebGL 2 API](../webgl_api) creates a new [`WebGLSync`](../webglsync) object and inserts it into the GL command stream.

Syntax
------

    WebGLSync gl.fenceSync(condition, flags);

### Parameters

`condition`  
A [`GLenum`](../webgl_api/types) specifying the condition that must be met to set the sync object's state to signaled. Must be `gl.SYNC_GPU_COMMANDS_COMPLETE`.

flags  
A [`GLbitfield`](../webgl_api/types) specifying a bitwise combination of flags controlling the behavior of the sync object. Must be `0` (exists for extensions only).

### Return value

A [`WebGLSync`](../webglsync) object.

Examples
--------

`gl` must be a [`WebGL2RenderingContext`](../webgl2renderingcontext). `WebGLSync` objects are not available in WebGL 1.

    var sync = gl.fenceSync(gl.SYNC_GPU_COMMANDS_COMPLETE, 0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.14">WebGL 2.0<br />
<span class="small">The definition of 'fenceSync' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glFenceSync.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glFenceSync' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`fenceSync`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/fenceSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/fenceSync</a>
