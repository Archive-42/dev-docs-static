# OES_vertex_array_object.bindVertexArrayOES()

The `OES_vertex_array_object.bindVertexArrayOES()` method of the [WebGL API](../webgl_api) binds a passed [`WebGLVertexArrayObject`](../webglvertexarrayobject) object to the buffer.

## Syntax

    void ext.bindVertexArrayOES(arrayObject);

### Parameters

arrayObject  
A [`WebGLVertexArrayObject`](../webglvertexarrayobject) (VAO) object to bind.

### Return value

None.

## Examples

    var ext = gl.getExtension('OES_vertex_array_object');
    var vao = ext.createVertexArrayOES();
    ext.bindVertexArrayOES(vao);

    // ...
    // calls to bindBuffer or vertexAttribPointer
    // which will be "recorded" in the VAO
    // ...

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/OES_vertex_array_object/">OES_vertex_array_object<br />
<span class="small">The definition of 'OES_vertex_array_object' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`bindVertexArrayOES`

24

17

25

No

15

8

≤37

25

?

14

8

1.5

## See also

- [`WebGLRenderingContext.getExtension()`](../webglrenderingcontext/getextension)
- [`WebGLRenderingContext.vertexAttribPointer()`](../webglrenderingcontext/vertexattribpointer)
- WebGL2 equivalent: [`WebGL2RenderingContext.bindVertexArray()`](../webgl2renderingcontext/bindvertexarray)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OES_vertex_array_object/bindVertexArrayOES" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OES_vertex_array_object/bindVertexArrayOES</a>
