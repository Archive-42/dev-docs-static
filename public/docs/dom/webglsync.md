WebGLSync
=========

The `WebGLSync` interface is part of the [WebGL 2](webgl_api) API and is used to synchronize activities between the GPU and the application.

When working with `WebGLSync` objects, the following methods of the [`WebGL2RenderingContext`](webgl2renderingcontext) are useful:

-   [`WebGL2RenderingContext.fenceSync()`](webgl2renderingcontext/fencesync)
-   [`WebGL2RenderingContext.deleteSync()`](webgl2renderingcontext/deletesync)
-   [`WebGL2RenderingContext.isSync()`](webgl2renderingcontext/issync)
-   [`WebGL2RenderingContext.clientWaitSync()`](webgl2renderingcontext/clientwaitsync)
-   [`WebGL2RenderingContext.waitSync()`](webgl2renderingcontext/waitsync)
-   [`WebGL2RenderingContext.getSyncParameter()`](webgl2renderingcontext/getsyncparameter)

Examples
--------

### Creating a `WebGLSync` object

in this example, `gl` must be a [`WebGL2RenderingContext`](webgl2renderingcontext). `WebGLSync` objects are not available in WebGL 1.

    var sync = gl.fenceSync(gl.SYNC_GPU_COMMANDS_COMPLETE, 0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.4">WebGL 2.0<br />
<span class="small">The definition of 'WebGLSync' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLSync`

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

-   [`WebGLRenderingContext.finish()`](webglrenderingcontext/finish)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLSync</a>
