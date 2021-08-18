WebGLRenderingContext.disableVertexAttribArray()
================================================

The `WebGLRenderingContext.disableVertexAttribArray()` method of the [WebGL API](../webgl_api) turns the generic vertex attribute array off at a given index position.

Syntax
------

    void gl.disableVertexAttribArray(index);

### Parameters

index  
A [`GLuint`](../webgl_api/types) specifying the index of the vertex attribute to disable.

### Return value

None.

Examples
--------

    gl.disableVertexAttribArray(0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.10">WebGL 1.0<br />
<span class="small">The definition of 'disableVertexAttribArray' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glEnableVertexAttribArray.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDisableVertexAttribArray' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`disableVertexAttribArray`

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

-   [`WebGLRenderingContext.enableVertexAttribArray()`](enablevertexattribarray)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/disableVertexAttribArray" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/disableVertexAttribArray</a>
