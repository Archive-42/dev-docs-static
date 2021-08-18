HTMLCanvasElement: webglcontextcreationerror event
==================================================

The `webglcontextcreationerror` event of the [WebGL API](../webgl_api) is fired if the user agent is unable to create a [`WebGLRenderingContext`](../webglrenderingcontext) context.

This event has a [`WebGLContextEvent.statusMessage`](../webglcontextevent/statusmessage) property, which can contain a platform dependent string with more information about the failure.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../webglcontextevent"><code>WebGLContextEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td>none</td></tr></tbody></table>

Example
-------

    var canvas = document.getElementById('canvas');

    canvas.addEventListener('webglcontextcreationerror', function(e) {
      console.log(e.statusMessage || 'Unknown error');
    }, false);

    var gl = canvas.getContext('webgl');
    // logs statusMessage or "Unknown error" if unable to create WebGL context

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.15.4">WebGL 1.0<br />
<span class="small">The definition of 'webglcontextcreationerror' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`webglcontextcreationerror_event`

9

12

49

11

12

5.1

≤37

25

49

12

8

1.5

See also
--------

-   [`WebGLContextEvent`](../webglcontextevent)
-   [`WebGLRenderingContext.isContextLost()`](../webglrenderingcontext/iscontextlost)
-   [`WEBGL_lose_context`](../webgl_lose_context), [`WEBGL_lose_context.loseContext()`](../webgl_lose_context/losecontext), [`WEBGL_lose_context.restoreContext()`](../webgl_lose_context/restorecontext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/webglcontextcreationerror_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/webglcontextcreationerror_event</a>
