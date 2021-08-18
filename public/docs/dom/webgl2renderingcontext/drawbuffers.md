WebGL2RenderingContext.drawBuffers()
====================================

The `WebGL2RenderingContext.drawBuffers()` method of the [WebGL 2 API](../webgl_api) defines draw buffers to which fragment colors are written into. The draw buffer settings are part of the state of the currently bound framebuffer or the drawingbuffer if no framebuffer is bound.

Syntax
------

    void gl.drawBuffers(buffers);

### Parameters

`buffers`  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLenum`](../webgl_api/types) specifying the buffers into which fragment colors will be written. Possible values are:

-   `gl.NONE`: Fragment shader output is not written into any color buffer.
-   `gl.BACK`: Fragment shader output is written into the back color buffer.
-   `gl.COLOR_ATTACHMENT{0-15}`: Fragment shader output is written in the nth color attachment of the current framebuffer.

### Return value

None.

### Exceptions

-   If `buffers` contains not one of the accepted values, a `gl.INVALID_ENUM` error is thrown.

Examples
--------

    gl.drawBuffers([gl.NONE, gl.COLOR_ATTACHMENT1]);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.11">WebGL 2.0<br />
<span class="small">The definition of 'drawBuffers' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glDrawBuffers.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glDrawBuffers' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`drawBuffers`

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

-   [`WebGL2RenderingContext.clearBuffer[fiuv]()`](clearbuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/drawBuffers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/drawBuffers</a>
