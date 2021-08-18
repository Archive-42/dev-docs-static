WebGLRenderingContext.getActiveAttrib()
=======================================

The `WebGLRenderingContext.getActiveAttrib()` method of the [WebGL API](../webgl_api) returns a [`WebGLActiveInfo`](../webglactiveinfo) object containing size, type, and name of a vertex attribute. It is generally used when querying unknown attributes either for debugging or generic library creation.

Syntax
------

    WebGLActiveInfo gl.getActiveAttrib(program,index);

### Parameters

program  
A [`WebGLProgram`](../webglprogram) containing the vertex attribute.

index  
A [`GLuint`](../webgl_api/types) specifying the index of the vertex attribute to get. This value is an index 0 to N - 1 as returned by [`gl.getProgramParameter(program, gl.ACTIVE_ATTRIBUTES)`](getprogramparameter).

### Return value

A [`WebGLActiveInfo`](../webglactiveinfo) object.

Examples
--------

    const numAttribs = gl.getProgramParameter(program, gl.ACTIVE_ATTRIBUTES);
    for (let i = 0; i < numAttribs; ++i) {
      const info = gl.getActiveAttrib(program, i);
      console.log('name:', info.name, 'type:', info.type, 'size:', info.size);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.10">WebGL 1.0<br />
<span class="small">The definition of 'getActiveAttrib' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetActiveAttrib.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetActiveAttrib' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`getActiveAttrib`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getActiveAttrib" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getActiveAttrib</a>
