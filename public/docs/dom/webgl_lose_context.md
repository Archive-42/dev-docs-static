WEBGL\_lose\_context
====================

The **WEBGL\_lose\_context** extension is part of the [WebGL API](webgl_api) and exposes functions to simulate losing and restoring a [`WebGLRenderingContext`](webglrenderingcontext).

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

Methods
-------

[`WEBGL_lose_context.loseContext()`](webgl_lose_context/losecontext)  
Simulates losing the context.

[`WEBGL_lose_context.restoreContext()`](webgl_lose_context/restorecontext)  
Simulates restoring the context.

Examples
--------

With this extension, you can simulate the `webglcontextlost` and `webglcontextrestored` events:

    const canvas = document.getElementById('canvas');
    const gl = canvas.getContext('webgl');

    canvas.addEventListener('webglcontextlost', (event) => {
      console.log(event);
    });

    gl.getExtension('WEBGL_lose_context').loseContext();

    // WebGLContextEvent event with type "webglcontextlost" is logged.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_lose_context/">WEBGL_lose_context<br />
<span class="small">The definition of 'WEBGL_lose_context' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WEBGL_lose_context`

26

17

22

19-58

No

15

8

≤37

26

?

14

8

1.5

See also
--------

-   [`WebGLRenderingContext.isContextLost()`](webglrenderingcontext/iscontextlost)
-   Events: `webglcontextlost`, `webglcontextrestored`, `webglcontextcreationerror`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_lose_context" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_lose_context</a>
