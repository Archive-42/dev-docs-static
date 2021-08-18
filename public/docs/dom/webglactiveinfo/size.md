WebGLActiveInfo.size
====================

The read-only `WebGLActiveInfo.size` property is a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the size of the requested data returned by calling the [`getActiveAttrib()`](../webglrenderingcontext/getactiveattrib) or [`getActiveUniform()`](../webglrenderingcontext/getactiveuniform) methods.

Examples
--------

    var activeAttrib = gl.getActiveAttrib(program, index);
    activeAttrib.size;

    var activeUniform = gl.getActiveUniform(program, index);
    activeUniform.size;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#DOM-WebGLActiveInfo-size">WebGL 1.0<br />
<span class="small">The definition of 'WebGLActiveInfo.size' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`size`

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

-   [`WebGLActiveInfo`](../webglactiveinfo)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLActiveInfo/size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLActiveInfo/size</a>
