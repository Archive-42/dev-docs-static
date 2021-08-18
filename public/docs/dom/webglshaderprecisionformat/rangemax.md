WebGLShaderPrecisionFormat.rangeMax
===================================

The read-only `WebGLShaderPrecisionFormat.rangeMax` property returns the base 2 log of the absolute value of the maximum value that can be represented.

Examples
--------

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');

    gl.getShaderPrecisionFormat(gl.VERTEX_SHADER, gl.MEDIUM_FLOAT).rangeMax; // 127
    gl.getShaderPrecisionFormat(gl.FRAGMENT_SHADER, gl.LOW_INT).rangeMax; // 24

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#DOM-WebGLShaderPrecisionFormat-rangeMax">WebGL 1.0<br />
<span class="small">The definition of 'WebGLShaderPrecisionFormat.rangeMax' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`rangeMax`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLShaderPrecisionFormat/rangeMax" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLShaderPrecisionFormat/rangeMax</a>
