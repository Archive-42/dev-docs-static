WebGLShaderPrecisionFormat.precision
====================================

The read-only `WebGLShaderPrecisionFormat.precision` property returns the number of bits of precision that can be represented.

For integer formats this value is always 0.

Examples
--------

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');

    gl.getShaderPrecisionFormat(gl.VERTEX_SHADER, gl.MEDIUM_FLOAT).precision; // 23
    gl.getShaderPrecisionFormat(gl.FRAGMENT_SHADER, gl.LOW_INT).precision; // 0

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#DOM-WebGLShaderPrecisionFormat-precision">WebGL 1.0<br />
<span class="small">The definition of 'WebGLShaderPrecisionFormat.precision' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`precision`

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

-   [`WebGLShaderPrecisionFormat`](../webglshaderprecisionformat)
-   [`WebGLRenderingContext.getShaderPrecisionFormat()`](../webglrenderingcontext/getshaderprecisionformat)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLShaderPrecisionFormat/precision" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLShaderPrecisionFormat/precision</a>
