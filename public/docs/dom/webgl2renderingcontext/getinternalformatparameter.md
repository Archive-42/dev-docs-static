WebGL2RenderingContext.getInternalformatParameter()
===================================================

The `WebGL2RenderingContext.getInternalformatParameter()` method of the [WebGL 2 API](../webgl_api) returns information about implementation-dependent support for internal formats.

Syntax
------

    any gl.getInternalformatParameter(target, internalformat, pname);

### Parameters

`target`  
A [`Glenum`](../webgl_api/types) specifying the target renderbuffer object. Possible values:

-   `gl.RENDERBUFFER`: Buffer data storage for single images in a renderable internal format.

`internalformat`  
A [`GLenum`](../webgl_api/types) specifying the internal format about which to retrieve information (must be a color-renderable, depth-renderable or stencil-renderable format).

`pname`  
A [`GLenum`](../webgl_api/types) specifying the type of information to query. Possible values:

-   `gl.SAMPLES`: Returns a [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array) containing sample counts supported for `internalformat` in descending order.

### Return value

Depends on the requested information (as specified with `pname`). It is an [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array) if `pname` is `gl.SAMPLES`.

Examples
--------

    var samples = gl.getInternalformatParameter(gl.RENDERBUFFER,
                                                gl.RGBA8, gl.SAMPLES);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.5">WebGL 2.0<br />
<span class="small">The definition of 'getInternalFormatParameter' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetInternalformativ.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetInternalformativ' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getInternalformatParameter`

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

-   [`WebGLRenderingContext.getRenderbufferParameter()`](../webglrenderingcontext/getrenderbufferparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getInternalformatParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getInternalformatParameter</a>
