WebGLRenderingContext.enableVertexAttribArray()
===============================================

The [`WebGLRenderingContext`](../webglrenderingcontext) method `enableVertexAttribArray()`, part of the [WebGL API](../webgl_api), turns on the generic vertex attribute array at the specified index into the list of attribute arrays.

You can disable the attribute array by calling [`disableVertexAttribArray()`](disablevertexattribarray).

In WebGL, values that apply to a specific vertex are stored in [attributes](../webgl_api/data#attributes). These are only available to the JavaScript code and the vertex shader. Attributes are referenced by an index number into the list of attributes maintained by the GPU. Some vertex attribute indices may have predefined purposes, depending on the platform and/or the GPU. Others are assigned by the WebGL layer when you create the attributes.

Either way, since attributes cannot be used unless enabled, and are disabled by default, you need to call `enableVertexAttribArray()` to enable individual attributes so that they can be used. Once that's been done, other methods can be used to access the attribute, including [`vertexAttribPointer()`](vertexattribpointer), [`vertexAttrib*()`](vertexattrib), and [`getVertexAttrib()`](getvertexattrib).

Syntax
------

    void gl.enableVertexAttribArray(index);

### Parameters

`index`  
A [`GLuint`](../webgl_api/types) specifying the index number that uniquely identifies the vertex attribute to enable. If you know the name of the attribute but not its index, you can get the index by calling [`getAttribLocation()`](getattriblocation).

### Return value

`undefined`.

### Errors

To check for errors after calling `enableVertexAttribArray()`, call [`getError()`](geterror).

`WebGLRenderingContext.INVALID_VALUE`  
The specified `index` is invalid; that is, it's greater than or equal to the maximum number of entries permitted in the context's vertex attribute list, as indicated by the value of `WebGLRenderingContext.MAX_VERTEX_ATTRIBS`.

Example
-------

This code — a snippet taken from the full example [A basic 2D WebGL animation example](../webgl_api/basic_2d_animation_example) — shows the use of `enableVertexArray()` to activate the attribute that will be used by the WebGL layer to pass individual vertexes from the vertex buffer into the vertex shader function.

    gl.bindBuffer(gl.ARRAY_BUFFER, vertexBuffer);

    aVertexPosition =
        gl.getAttribLocation(shaderProgram, "aVertexPosition");

    gl.enableVertexAttribArray(aVertexPosition);
    gl.vertexAttribPointer(aVertexPosition, vertexNumComponents,
          gl.FLOAT, false, 0, 0);

    gl.drawArrays(gl.TRIANGLES, 0, vertexCount);

### Note

This code snippet is taken from [the function `animateScene()`](../webgl_api/basic_2d_animation_example#drawing_and_animating_the_scene) in "A basic 2D WebGL animation example." See that article for the full sample and to see the resulting animation in action.

This code sets the buffer of vertexes that will be used to draw the triangles of the shape by calling [`bindBuffer()`](bindbuffer). Then the vertex position attribute's index is obtained from the shader program by calling [`getAttribLocation()`](getattriblocation).

With the index of the vertex position attribute now available in `aVertexPosition`, we call `enableVertexAttribArray()` to enable the position attribute so it can be used by the shader program (in particular, by the vertex shader).

Then the vertex buffer is bound to the `aVertexPosition` attribute by calling [`vertexAttribPointer()`](vertexattribpointer). This step is not obvious, since this binding is almost a side effect. But as a result, accessing `aVertexPosition` now obtains data from the vertex buffer.

With the association in place between the vertex buffer for our shape and the `aVertexPosition` attribute used to deliver vertexes one by one into the vertex shader, we're ready to draw the shape by calling [`drawArrays()`](drawarrays).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.10">WebGL 1.0<br />
<span class="small">The definition of 'enableVertexAttribArray' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glEnableVertexAttribArray.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glEnableVertexAttribArray' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`enableVertexAttribArray`

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

-   [Data in WebGL](../webgl_api/data)
-   [Adding 2D content to a WebGL context](../webgl_api/tutorial/adding_2d_content_to_a_webgl_context)
-   [A basic 2D WebGL animation sample](../webgl_api/basic_2d_animation_example)
-   [`disableVertexAttribArray()`](disablevertexattribarray)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/enableVertexAttribArray" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/enableVertexAttribArray</a>
