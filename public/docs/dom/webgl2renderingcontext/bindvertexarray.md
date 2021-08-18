WebGL2RenderingContext.bindVertexArray()
========================================

The `WebGL2RenderingContext.bindVertexArray()` method of the [WebGL 2 API](../webgl_api) binds a passed [`WebGLVertexArrayObject`](../webglvertexarrayobject) object to the buffer.

Syntax
------

    void gl.bindVertexArray(vertexArray);

### Parameters

vertexArray  
A [`WebGLVertexArrayObject`](../webglvertexarrayobject) (VAO) object to bind.

### Return value

None.

Examples
--------

    var vao = gl.createVertexArray();
    gl.bindVertexArray(vao);

    // ...
    // calls to bindBuffer or vertexAttribPointer
    // which will be "recorded" in the VAO
    // ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.17">WebGL 2.0<br />
<span class="small">The definition of 'bindVertexArray' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBindVertexArray.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBindVertexArray' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`bindVertexArray`

56

79

51

No

43

No

58

58

51

43

No

7.0

See also
--------

-   [`WebGLVertexArrayObject`](../webglvertexarrayobject)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/bindVertexArray" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/bindVertexArray</a>
