WebGLRenderingContext.isContextLost()
=====================================

The `WebGLRenderingContext.isContextLost()` method returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether or not the WebGL context has been lost and must be re-established before rendering can resume.

Syntax
------

    let isLost = gl.isContextLost();

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which is `true` if the context is lost, or `false` if not.

Usage notes
-----------

There are several reasons why a WebGL context may be lost, making it necessary to re-establish the context before resuming rendering. Examples include:

-   Two or more pages are using the GPU, but together place too high a demand on the GPU, so the browser tells the two contexts that they've lost the connection, then selects one of the two to restore access for.
-   The user's computer has multiple graphics processors (such as a laptop with both mobile and desktop class GPUs, the former used primarily when on battery power), and the user or system decides to switch GPUs. In this case, all contexts are lost, then restored after switching GPUs.
-   Another page running in the user's browser performs an operation using the GPU that takes too long, causing hte browser to decide to reset the GPU in order to break the stall. This would cause every WebGL context to be lost throughout the entire browser.
-   The user updates their graphics driver on an operating system that allows graphics drivers to be updated without restarting the system.

Examples
--------

For example, when checking for program linking success, you could also check if the context is not lost:

    gl.linkProgram(program);

    if (!gl.getProgramParameter(program, gl.LINK_STATUS) && !gl.isContextLost()) {
      var info = gl.getProgramInfoLog(program);
      console.log('Error linking program:\n' + info);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.13">WebGL 1.0<br />
<span class="small">The definition of 'WebGLRenderingContext.isContextLost' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`isContextLost`

9

12

4

11

12

5.1

≤37

25

Yes

12

8

1.5

See also
--------

-   The [`WebGLContextEvent`](../webglcontextevent) signals changes in the context state.
-   [Handling lost context in WebGL](https://www.khronos.org/webgl/wiki/HandlingContextLost): Khronos WebGL wiki

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/isContextLost" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/isContextLost</a>
