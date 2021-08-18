WebGLTexture
============

The **WebGLTexture** interface is part of the [WebGL API](webgl_api) and represents an opaque texture object providing storage and state for texturing operations.

Description
-----------

The `WebGLTexture` object does not define any methods or properties of its own and its content is not directly accessible. When working with `WebGLTexture` objects, the following methods of the [`WebGLRenderingContext`](webglrenderingcontext) are useful:

-   [`WebGLRenderingContext.bindTexture()`](webglrenderingcontext/bindtexture)
-   [`WebGLRenderingContext.createTexture()`](webglrenderingcontext/createtexture)
-   [`WebGLRenderingContext.deleteTexture()`](webglrenderingcontext/deletetexture)
-   [`WebGLRenderingContext.isTexture()`](webglrenderingcontext/istexture)

Examples
--------

### Creating a texture

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var texture = gl.createTexture();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.9">WebGL 1.0<br />
<span class="small">The definition of 'WebGLTexture' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLTexture`

9

12

4

11

12

5.1

Yes

25

Yes

12

8

1.5

`worker_support`

No

No

44

No

No

No

No

No

No

No

No

No

See also
--------

-   [`WebGLRenderingContext.bindTexture()`](webglrenderingcontext/bindtexture)
-   [`WebGLRenderingContext.createTexture()`](webglrenderingcontext/createtexture)
-   [`WebGLRenderingContext.deleteTexture()`](webglrenderingcontext/deletetexture)
-   [`WebGLRenderingContext.isTexture()`](webglrenderingcontext/istexture)
-   [`WebGLRenderingContext.compressedTexImage2D()`](webglrenderingcontext/compressedteximage2d)
-   [`WebGLRenderingContext.compressedTexSubImage2D()`](webglrenderingcontext/compressedtexsubimage2d)
-   [`WebGLRenderingContext.copyTexImage2D()`](webglrenderingcontext/copyteximage2d)
-   [`WebGLRenderingContext.copyTexSubImage2D()`](webglrenderingcontext/copytexsubimage2d)
-   [`WebGLRenderingContext.generateMipmap()`](webglrenderingcontext/generatemipmap)
-   [`WebGLRenderingContext.getTexParameter()`](webglrenderingcontext/gettexparameter)
-   [`WebGLRenderingContext.texImage2D()`](webglrenderingcontext/teximage2d)
-   [`WebGLRenderingContext.texSubImage2D()`](webglrenderingcontext/texsubimage2d)
-   [`WebGLRenderingContext.texParameterf()`](webglrenderingcontext/texparameter)
-   [`WebGLRenderingContext.texParameteri()`](webglrenderingcontext/texparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLTexture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLTexture</a>
