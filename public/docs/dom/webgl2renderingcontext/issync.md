WebGL2RenderingContext.isSync()
===============================

The `WebGL2RenderingContext.isSync()` method of the [WebGL 2 API](../webgl_api) returns `true` if the passed object is a valid [`WebGLSync`](../webglsync) object.

Syntax
------

    GLboolean gl.isSync(sync);

### Parameters

`sync`  
A [`WebGLSync`](../webglsync) object to test.

### Return value

A [`GLboolean`](../webgl_api/types) indicating whether the given object is a valid [`WebGLSync`](../webglsync) object (`true`) or not (`false`).

Examples
--------

`gl` must be a [`WebGL2RenderingContext`](../webgl2renderingcontext). `WebGLSync` objects are not available in WebGL 1.

    var sync = gl.fenceSync(gl.SYNC_GPU_COMMANDS_COMPLETE, 0);

    // ...

    gl.isSync(sync);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.14">WebGL 2.0<br />
<span class="small">The definition of 'isSync' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glIsSync.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glIsSync' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`isSync`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/isSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/isSync</a>
