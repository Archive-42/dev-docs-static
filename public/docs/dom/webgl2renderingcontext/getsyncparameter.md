WebGL2RenderingContext.getSyncParameter()
=========================================

The `WebGL2RenderingContext.getSyncParameter()` method of the [WebGL 2 API](../webgl_api) returns parameter information of a [`WebGLSync`](../webglsync) object.

Syntax
------

    any gl.getSyncParameter(sync, pname);

### Parameters

sync  
A [`WebGLSync`](../webglsync) object.

`pname`  
A [`GLenum`](../webgl_api/types) specifying which information to return. Possible values:

-   `gl.OBJECT_TYPE`: Returns a [`GLenum`](../webgl_api/types) indicating the type of the sync object (always `gl.SYNC_FENCE`).
-   `gl.SYNC_STATUS`: Returns a [`GLenum`](../webgl_api/types) indicating the status of the sync object (`gl.SIGNALED` or `gl.UNSIGNALED`).
-   `gl.SYNC_CONDITION`: Returns a [`GLenum`](../webgl_api/types) indicating the sync objects' condition (always `gl.SYNC_GPU_COMMANDS_COMPLETE`).
-   `gl.SYNC_FLAGS`: Returns a [`GLenum`](../webgl_api/types) indicating the flags with which the sync object was created (always 0 as no flags are supported).

### Return value

Depends on the `pname` parameter, either a [`GLenum`](../webgl_api/types) or a [`GLbitfield`](../webgl_api/types).

Examples
--------

    var sync = gl.fenceSync(gl.SYNC_GPU_COMMANDS_COMPLETE, 0);
    gl.getSyncParameter(sync, gl.SYNC_STATUS);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.14">WebGL 2.0<br />
<span class="small">The definition of 'getSyncParameter' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetSynciv.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetSynciv' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getSyncParameter`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getSyncParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getSyncParameter</a>
