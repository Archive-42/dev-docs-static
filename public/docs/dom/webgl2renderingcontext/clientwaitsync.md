WebGL2RenderingContext.clientWaitSync()
=======================================

The `WebGL2RenderingContext.clientWaitSync()` method of the [WebGL 2 API](../webgl_api) blocks and waits for a [`WebGLSync`](../webglsync) object to become signaled or a given timeout to be passed.

Syntax
------

    GLenum gl.clientWaitSync(sync, flags, timeout);

### Parameters

`sync`  
A [`WebGLSync`](../webglsync) object on which to wait on.

flags  
A [`GLbitfield`](../webgl_api/types) specifying a bitwise combination of flags controlling the flushing behavior. May be `gl.SYNC_FLUSH_COMMANDS_BIT`.

timeout  
A [`GLint64`](../webgl_api/types) specifying a timeout (in nanoseconds) for which to wait for the sync object to become signaled. Must not be larger than `gl.MAX_CLIENT_WAIT_TIMEOUT_WEBGL`.

### Return value

A [`GLenum`](../webgl_api/types) indicating the sync object's status.

-   `gl.ALREADY_SIGNALED`: Indicates that the sync object was signaled when this method was called.
-   `gl.TIMEOUT_EXPIRED`: Indicates that the `timeout` time passed and that the sync object did not become signaled.
-   `gl.CONDITION_SATISFIED`: Indicates that the sync object was signaled before the `timeout` expired.
-   `gl.WAIT_FAILED`: Indicates that an error occurred during the execution.

Examples
--------

    var sync = gl.fenceSync(gl.SYNC_GPU_COMMANDS_COMPLETE, 0);
    var status = gl.clientWaitSync(sync, 0, 0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.14">WebGL 2.0<br />
<span class="small">The definition of 'clientWaitSync' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glClientWaitSync.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glClientWaitSync' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`clientWaitSync`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/clientWaitSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/clientWaitSync</a>
