WebGLRenderingContext.blendColor()
==================================

The `WebGLRenderingContext.blendColor()` method of the [WebGL API](../webgl_api) is used to set the source and destination blending factors.

Syntax
------

    void gl.blendColor(red, green, blue, alpha);

### Parameters

`red`  
A [`GLclampf`](../webgl_api/types) for the red component in the range of 0 to 1.

`green`  
A [`GLclampf`](../webgl_api/types) for the green component in the range of 0 to 1.

blue  
A [`GLclampf`](../webgl_api/types) for the blue component in the range of 0 to 1.

alpha  
A [`GLclampf`](../webgl_api/types) for the alpha component (transparency) in the range of 0 to 1.

### Return value

None.

Examples
--------

To set the blend color, use:

    gl.blendColor(0, 0.5, 1, 1);

To get the blend color, query the `BLEND_COLOR` constant which returns a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array).

    gl.getParameter(gl.BLEND_COLOR);
    // Float32Array[0, 0.5, 1, 1]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'blendColor' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glBlendColor.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glBlendColor' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`blendColor`

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

-   [`WebGLRenderingContext.blendEquation()`](blendequation)
-   [`WebGLRenderingContext.blendFunc()`](blendfunc)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/blendColor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/blendColor</a>
