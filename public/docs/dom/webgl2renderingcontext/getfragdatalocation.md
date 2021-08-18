WebGL2RenderingContext.getFragDataLocation()
============================================

The `WebGL2RenderingContext.getFragDataLocation()` method of the [WebGL 2 API](../webgl_api) returns the binding of color numbers to user-defined varying out variables.

Syntax
------

    GLint gl.getFragDataLocation(program, name);

### Parameters

program  
A [`WebGLProgram`](../webglprogram) to query.

name  
A [`DOMString`](../domstring) specifying the name of the user-defined varying out variable.

### Return value

A [`GLint`](../webgl_api/types) indicating the assigned color number binding, or `-1` otherwise.

Examples
--------

    // program is a linked WebGLProgram

    gl.getFragDataLocation(program, 'fragColor');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.7">WebGL 2.0<br />
<span class="small">The definition of 'getFragDataLocation' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetFragDataLocation.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetFragDataLocation' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getFragDataLocation`

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

-   [`WebGLRenderingContext.createProgram()`](../webglrenderingcontext/createprogram)
-   [`WebGLRenderingContext.deleteProgram()`](../webglrenderingcontext/deleteprogram)
-   [`WebGLRenderingContext.isProgram()`](../webglrenderingcontext/isprogram)
-   [`WebGLRenderingContext.linkProgram()`](../webglrenderingcontext/linkprogram)
-   [`WebGLRenderingContext.useProgram()`](../webglrenderingcontext/useprogram)
-   [`WebGLRenderingContext.validateProgram()`](../webglrenderingcontext/validateprogram)
-   [`WebGLRenderingContext.getProgramParameter()`](../webglrenderingcontext/getprogramparameter)
-   [`WebGLRenderingContext.getProgramInfoLog()`](../webglrenderingcontext/getprograminfolog)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getFragDataLocation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getFragDataLocation</a>
