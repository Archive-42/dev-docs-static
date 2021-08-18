WebGLRenderingContext.bindAttribLocation()
==========================================

The `WebGLRenderingContext.bindAttribLocation()` method of the [WebGL API](../webgl_api) binds a generic vertex index to an attribute variable.

Syntax
------

    void gl.bindAttribLocation(program, index, name);

### Parameters

`program`  
A [`WebGLProgram`](../webglprogram) object to bind.

index  
A [`GLuint`](../webgl_api/types) specifying the index of the generic vertex to bind.

name  
A [`DOMString`](../domstring) specifying the name of the variable to bind to the generic vertex index. This name cannot start with "webgl\_" or "\_webgl\_", as these are reserved for use by WebGL.

### Return value

None.

Examples
--------

    gl.bindAttribLocation(program, colorLocation, 'vColor');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'bindAttribLocation' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glBindAttribLocation.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glBindAttribLocation' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`bindAttribLocation`

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

-   [`WebGLRenderingContext.getActiveAttrib()`](getactiveattrib)
-   [`WebGLRenderingContext.getAttribLocation()`](getattriblocation)
-   [`WebGLRenderingContext.getVertexAttrib()`](getvertexattrib)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bindAttribLocation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bindAttribLocation</a>
