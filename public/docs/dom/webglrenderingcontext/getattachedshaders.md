WebGLRenderingContext.getAttachedShaders()
==========================================

The `WebGLRenderingContext.getAttachedShaders()` method of the [WebGL API](../webgl_api) returns a list of [`WebGLShader`](../webglshader) objects attached to a [`WebGLProgram`](../webglprogram).

Syntax
------

    sequence<WebGLShader> gl.getAttachedShaders(program);

### Parameters

program  
A [`WebGLProgram`](../webglprogram) object to get attached shaders for.

### Return value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`WebGLShader`](../webglshader) objects that are attached to the given `WebGLProgram`.

Examples
--------

    var program = gl.createProgram();

    // Attach pre-existing shaders
    gl.attachShader(program, vertexShader);
    gl.attachShader(program, fragmentShader);
    gl.linkProgram(program);

    gl.getAttachedShaders(program);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.9">WebGL 1.0<br />
<span class="small">The definition of 'getAttachedShaders' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetAttachedShaders.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetAttachedShaders' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getAttachedShaders`

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

-   [`WebGLRenderingContext.createShader()`](createshader)
-   [`WebGLRenderingContext.isShader()`](isshader)
-   [`WebGLRenderingContext.deleteShader()`](deleteshader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getAttachedShaders" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getAttachedShaders</a>
