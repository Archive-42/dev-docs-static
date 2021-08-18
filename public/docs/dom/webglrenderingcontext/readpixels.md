WebGLRenderingContext.readPixels()
==================================

The `WebGLRenderingContext.readPixels()` method of the [WebGL API](../webgl_api) reads a block of pixels from a specified rectangle of the current color framebuffer into an [`ArrayBufferView`](../arraybufferview) object.

Syntax
------

    // WebGL1:
    void gl.readPixels(x, y, width, height, format, type, pixels);

    // WebGL2:
    void gl.readPixels(x, y, width, height, format, type, GLintptr offset);
    void gl.readPixels(x, y, width, height, format, type, ArrayBufferView pixels, GLuint dstOffset);

### Parameters

x  
A [`GLint`](../webgl_api/types) specifying the first horizontal pixel that is read from the lower left corner of a rectangular block of pixels.

y  
A [`GLint`](../webgl_api/types) specifying the first vertical pixel that is read from the lower left corner of a rectangular block of pixels.

width  
A [`GLsizei`](../webgl_api/types) specifying the width of the rectangle.

height  
A [`GLsizei`](../webgl_api/types) specifying the height of the rectangle.

format  
A [`GLenum`](../webgl_api/types) specifying the format of the pixel data. Possible values:

-   `gl.ALPHA`: Discards the red, green and blue components and reads the alpha component.
-   `gl.RGB`: Discards the alpha components and reads the red, green and blue components.
-   `gl.RGBA`: Red, green, blue and alpha components are read from the color buffer.

WebGL2 adds

-   `gl.RED`
-   `gl.RG`
-   `gl.RED_INTEGER`
-   `gl.RG_INTEGER`
-   `gl.RGB_INTEGER`
-   `gl.RGBA_INTEGER`

type  
A [`GLenum`](../webgl_api/types) specifying the data type of the pixel data. Possible values:

-   `gl.UNSIGNED_BYTE`
-   `gl.UNSIGNED_SHORT_5_6_5`
-   `gl.UNSIGNED_SHORT_4_4_4_4`
-   `gl.UNSIGNED_SHORT_5_5_5_1`
-   `gl.FLOAT`

WebGL2 adds

-   `gl.BYTE`
-   `gl.UNSIGNED_INT_2_10_10_10_REV`
-   `gl.HALF_FLOAT`
-   `gl.SHORT`
-   `gl.UNSIGNED_SHORT`
-   `gl.INT`
-   `gl.UNSIGNED_INT`
-   `gl.UNSIGNED_INT_10F_11F_11F_REV`
-   `gl.UNSIGNED_INT_5_9_9_9_REV`

pixels  
An [`ArrayBufferView`](../arraybufferview) object to read data into. The array type must match the type of the `type` parameter.

-   [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) for `gl.UNSIGNED_BYTE`.
-   [`Uint16Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint16Array) for `gl.UNSIGNED_SHORT_5_6_5`, `gl.UNSIGNED_SHORT_4_4_4_4`, or `gl.UNSIGNED_SHORT_5_5_5_1`.
-   [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) for `gl.FLOAT`.

 `dstOffset` <span class="badge inline optional">Optional</span>   
Offset. Defaults to 0.

### Return value

None.

### Exceptions

-   A `gl.INVALID_ENUM` error is thrown if `format` or `type` is not an accepted value.
-   A `gl.INVALID_OPERATION` error is thrown if
    -   `type` is `gl.UNSIGNED_SHORT_5_6_5` and `format` is not `gl.RGB`.
    -   `type` is `gl.UNSIGNED_SHORT_4_4_4_4` and `format` is not `gl.RGB`A.
    -   `type` does not match the typed array type of `pixels`.
-   A `gl.INVALID_FRAMEBUFFER_OPERATION` error is thrown if the currently bound framebuffer is not framebuffer complete.

Examples
--------

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var pixels = new Uint8Array(gl.drawingBufferWidth * gl.drawingBufferHeight * 4);
    gl.readPixels(0, 0, gl.drawingBufferWidth, gl.drawingBufferHeight, gl.RGBA, gl.UNSIGNED_BYTE, pixels);
    console.log(pixels); // Uint8Array

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.12">WebGL 1.0<br />
<span class="small">The definition of 'readPixels' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glReadPixels.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glReadPixels' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`readPixels`

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

`WebGL2`

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

-   [Typed Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/readPixels" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/readPixels</a>
