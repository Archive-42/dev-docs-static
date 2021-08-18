WebGLRenderingContext.activeTexture()
=====================================

The `WebGLRenderingContext.activeTexture()` method of the [WebGL API](../webgl_api) specifies which texture unit to make active.

Syntax
------

    void gl.activeTexture(texture);

### Parameters

`texture`  
The texture unit to make active. The value is a `gl.TEXTUREI` where *I* is within the range from 0 to `gl.MAX_COMBINED_TEXTURE_IMAGE_UNITS - 1`.

### Return value

None.

### Exceptions

If *texture* is not one of `gl.TEXTUREI`, where *I* is within the range from 0 to `gl.MAX_COMBINED_TEXTURE_IMAGE_UNITS - 1`, a `gl.INVALID_ENUM` error is thrown.

Examples
--------

The following call selects `gl.TEXTURE1` as the current texture. Subsequent calls that modify the texture state will affect this texture.

    gl.activeTexture(gl.TEXTURE1);

The number of texture units is implementation dependent, you can get this number with the help of the `MAX_COMBINED_TEXTURE_IMAGE_UNITS` constant. It is, per specification, at least 8.

    gl.getParameter(gl.MAX_COMBINED_TEXTURE_IMAGE_UNITS);

To get the active texture, query the `ACTIVE_TEXTURE` constant.

    gl.activeTexture(gl.TEXTURE0);
    gl.getParameter(gl.ACTIVE_TEXTURE);
    // returns "33984" (0x84C0, gl.TEXTURE0 enum value)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'activeTexture' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glActiveTexture.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glActiveTexture' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`activeTexture`

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

-   [`WebGLRenderingContext.getParameter()`](getparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/activeTexture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/activeTexture</a>
