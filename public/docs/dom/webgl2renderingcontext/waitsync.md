WebGL2RenderingContext.waitSync()
=================================

The `WebGL2RenderingContext.waitSync()` method of the [WebGL 2 API](../webgl_api) returns immediately, but waits on the GL server until the given [`WebGLSync`](../webglsync) object is signaled.

The method is a no-op in the absence of the possibility of synchronizing between multiple GL contexts.

Syntax
------

    void gl.waitSync(sync, flags, timeout);

### Parameters

`sync`  
A [`WebGLSync`](../webglsync) object on which to wait on.

flags  
A [`GLbitfield`](../webgl_api/types) specifying a bitwise combination of flags controlling the flushing behavior. Must be `0` (exists for extensions only).

timeout  
A [`GLint64`](../webgl_api/types) specifying a timeout the server should wait before continuing. Must be `gl.TIMEOUT_IGNORED`.

### Return value

None.

Examples
--------

    var sync = gl.fenceSync(gl.SYNC_GPU_COMMANDS_COMPLETE, 0);
    gl.waitSync(sync, 0, gl.TIMEOUT_IGNORED);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.14">WebGL 2.0<br />
<span class="small">The definition of 'waitSync' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glWaitSync.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glWaitSync' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`waitSync`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/waitSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/waitSync</a>
