WebGLRenderingContext.getAttribLocation()
=========================================

The `WebGLRenderingContext.getAttribLocation()` method of the [WebGL API](../webgl_api) returns the location of an attribute variable in a given [`WebGLProgram`](../webglprogram).

Syntax
------

    GLint gl.getAttribLocation(program, name);

### Parameters

program  
A [`WebGLProgram`](../webglprogram) containing the attribute variable.

name  
A [`DOMString`](../domstring) specifying the name of the attribute variable whose location to get.

### Return value

A [`GLint`](../webgl_api/types) number indicating the location of the variable name if found. Returns -1 otherwise.

Examples
--------

    gl.getAttribLocation(program, 'vColor');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.10">WebGL 1.0<br />
<span class="small">The definition of 'getAttribLocation' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetAttribLocation.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetAttribLocation' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Main page of the OpenGL API.</td></tr></tbody></table>

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

`getAttribLocation`

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

-   [`WebGLRenderingContext.getUniformLocation()`](getuniformlocation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getAttribLocation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getAttribLocation</a>
