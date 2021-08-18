WebGL2RenderingContext.isVertexArray()
======================================

The `WebGL2RenderingContext.isVertexArray()` method of the [WebGL API](../webgl_api) returns `true` if the passed object is a valid [`WebGLVertexArrayObject`](../webglvertexarrayobject) object.

Syntax
------

    GLBoolean gl.isVertexArray(vertexArray);

### Parameters

`vertexArray`  
A [`WebGLVertexArrayObject`](../webglvertexarrayobject) (VAO) object to test.

### Return value

A [`GLboolean`](../webgl_api/types) indicating whether the given object is a valid [`WebGLVertexArrayObject`](../webglvertexarrayobject) object (`true`) or not (`false`).

Examples
--------

    var vao = gl.createVertexArray();
    gl.bindVertexArray(vao);

    // ...

    gl.isVertexArray(vao);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.17">WebGL 2.0<br />
<span class="small">The definition of 'isVertexArray' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glIsVertexArray.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glIsVertexArray' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`isVertexArray`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/isVertexArray" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/isVertexArray</a>
