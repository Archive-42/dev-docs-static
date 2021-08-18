WEBGL\_lose\_context.loseContext()
==================================

The **WEBGL\_lose\_context.loseContext()** method is part of the [WebGL API](../webgl_api) and allows you to simulate losing the context of a [`WebGLRenderingContext`](../webglrenderingcontext) context.

It triggers the steps described in the WebGL specification for handling context lost. The context will remain lost until [`WEBGL_lose_context.restoreContext()`](restorecontext) is called.

Syntax
------

    gl.getExtension('WEBGL_lose_context').loseContext();

Examples
--------

With this method, you can simulate the `webglcontextlost` event:

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');

    canvas.addEventListener('webglcontextlost', function(e) {
      console.log(e);
    }, false);

    gl.getExtension('WEBGL_lose_context').loseContext();

    // WebGLContextEvent event with type "webglcontextlost" is logged.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_lose_context/">WEBGL_lose_context<br />
<span class="small">The definition of 'WEBGL_lose_context.loseContext' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`loseContext`

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

-   [`WebGLRenderingContext.isContextLost()`](../webglrenderingcontext/iscontextlost)
-   Events: `webglcontextlost`, `webglcontextrestored`, `webglcontextcreationerror`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_lose_context/loseContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_lose_context/loseContext</a>
