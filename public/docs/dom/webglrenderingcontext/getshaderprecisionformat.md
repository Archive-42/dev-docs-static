WebGLRenderingContext.getShaderPrecisionFormat()
================================================

The `WebGLRenderingContext.getShaderPrecisionFormat()` method of the [WebGL API](../webgl_api) returns a new [`WebGLShaderPrecisionFormat`](../webglshaderprecisionformat) object describing the range and precision for the specified shader numeric format.

Syntax
------

    WebGLShaderPrecisionFormat gl.getShaderPrecisionFormat(shaderType, precisionType);

### Parameters

`shaderType`  
Either a `gl.FRAGMENT_SHADER` or a `gl.VERTEX_SHADER`.

`precisionType`  
A precision type value. Either `gl.LOW_FLOAT`, `gl.MEDIUM_FLOAT`, `gl.HIGH_FLOAT`, `gl.LOW_INT`, `gl.MEDIUM_INT`, or `gl.HIGH_INT`.

### Return value

A [`WebGLShaderPrecisionFormat`](../webglshaderprecisionformat) object or `null`, if an error occurs.

### Exceptions

-   `gl.INVALID_ENUM` if the shader or precision types aren't recognized.
-   `gl.INVALID_OPERATION` if the shader compiler isn't supported.

Examples
--------

The following code gets the precision format of a `gl.VERTEX_SHADER` with a `gl.MEDIUM_FLOAT` precision type.

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');

    gl.getShaderPrecisionFormat(gl.VERTEX_SHADER, gl.MEDIUM_FLOAT);
    // WebGLShaderPrecisionFormat { rangeMin: 127, rangeMax: 127, precision: 23 }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'getShaderPrecisionFormat' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetShaderPrecisionFormat.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetShaderPrecisionFormat' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getShaderPrecisionFormat`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getShaderPrecisionFormat" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getShaderPrecisionFormat</a>
