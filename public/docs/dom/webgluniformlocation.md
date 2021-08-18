WebGLUniformLocation
====================

The **WebGLUniformLocation** interface is part of the [WebGL API](webgl_api) and represents the location of a uniform variable in a shader program.

Description
-----------

The `WebGLUniformLocation` object does not define any methods or properties of its own and its content is not directly accessible. When working with `WebGLUniformLocation` objects, the following methods of the [`WebGLRenderingContext`](webglrenderingcontext) are useful:

-   [`WebGLRenderingContext.getUniformLocation()`](webglrenderingcontext/getuniformlocation)
-   [`WebGLRenderingContext.uniform()`](webglrenderingcontext/uniform)

Examples
--------

### Getting an uniform location

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');

    var location = gl.getUniformLocation(WebGLProgram, 'uniformName');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.10">WebGL 1.0<br />
<span class="small">The definition of 'WebGLUniformLocation' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLUniformLocation`

9

12

4

11

12

5.1

Yes

25

Yes

12

8

1.5

`worker_support`

No

No

44

No

No

No

No

No

No

No

No

No

See also
--------

-   [`WebGLRenderingContext.getUniformLocation()`](webglrenderingcontext/getuniformlocation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLUniformLocation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLUniformLocation</a>
