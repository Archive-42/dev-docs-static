WebGLShaderPrecisionFormat
==========================

The **WebGLShaderPrecisionFormat** interface is part of the [WebGL API](webgl_api) and represents the information returned by calling the [`WebGLRenderingContext.getShaderPrecisionFormat()`](webglrenderingcontext/getshaderprecisionformat) method.

Properties
----------

 [`WebGLShaderPrecisionFormat.rangeMin`](webglshaderprecisionformat/rangemin) <span class="badge inline readonly">Read only </span>   
The base 2 log of the absolute value of the minimum value that can be represented.

 [`WebGLShaderPrecisionFormat.rangeMax`](webglshaderprecisionformat/rangemax) <span class="badge inline readonly">Read only </span>   
The base 2 log of the absolute value of the maximum value that can be represented.

 [`WebGLShaderPrecisionFormat.precision`](webglshaderprecisionformat/precision) <span class="badge inline readonly">Read only </span>   
The number of bits of precision that can be represented. For integer formats this value is always 0.

Examples
--------

A `WebGLShaderPrecisionFormat` object is returned by the [`WebGLRenderingContext.getShaderPrecisionFormat()`](webglrenderingcontext/getshaderprecisionformat) method.

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    gl.getShaderPrecisionFormat(gl.VERTEX_SHADER, gl.MEDIUM_FLOAT);
    // WebGLShaderPrecisionFormat { rangeMin: 127, rangeMax: 127, precision: 23 }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.12">WebGL 1.0<br />
<span class="small">The definition of 'WebGLShaderPrecisionFormat' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLShaderPrecisionFormat`

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

`rangeMin`

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

-   [`WebGLRenderingContext.getShaderPrecisionFormat()`](webglrenderingcontext/getshaderprecisionformat)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLShaderPrecisionFormat" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLShaderPrecisionFormat</a>
