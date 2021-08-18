WebGL2RenderingContext.vertexAttribDivisor()
============================================

The `WebGL2RenderingContext.vertexAttribDivisor()` method of the [WebGL 2 API](../webgl_api) modifies the rate at which generic vertex attributes advance when rendering multiple instances of primitives with [`gl.drawArraysInstanced()`](drawarraysinstanced) and [`gl.drawElementsInstanced()`](drawelementsinstanced).

**Note:** When using [WebGL 1](../webglrenderingcontext), the [`ANGLE_instanced_arrays`](../angle_instanced_arrays) extension can provide this method, too.

Syntax
------

    void gl.vertexAttribDivisor(index, divisor);

### Parameters

`index`  
A [`GLuint`](../webgl_api/types) specifying the index of the generic vertex attributes.

`divisor`  
A [`GLuint`](../webgl_api/types) specifying the number of instances that will pass between updates of the generic attribute.

### Return value

None.

Examples
--------

    gl.vertexAttribDivisor(0, 2);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.9">WebGL 2.0<br />
<span class="small">The definition of 'vertexAttribDivisor' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glVertexAttribDivisor.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glVertexAttribDivisor' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`vertexAttribDivisor`

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

-   [`ANGLE_instanced_arrays.vertexAttribDivisorANGLE()`](../angle_instanced_arrays/vertexattribdivisorangle)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/vertexAttribDivisor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/vertexAttribDivisor</a>
