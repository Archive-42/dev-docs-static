WebGLRenderingContext.hint()
============================

The `WebGLRenderingContext.hint()` method of the [WebGL API](../webgl_api) specifies hints for certain behaviors. The interpretation of these hints depend on the implementation.

Syntax
------

    void gl.hint(target, mode);

### Parameters

target  
Sets which behavior to be controlled. Possible values:

-   `gl.GENERATE_MIPMAP_HINT`: Quality of filtering when generating mipmap images with [`WebGLRenderingContext.generateMipmap()`](generatemipmap).
-   When using the [`OES_standard_derivatives`](../oes_standard_derivatives) extension:
    -   `ext.FRAGMENT_SHADER_DERIVATIVE_HINT_OES`: Accuracy of the derivative calculation for the GLSL built-in functions: `dFdx`, `dFdy`, and `fwidth`.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.FRAGMENT_SHADER_DERIVATIVE_HINT`: Same as `ext.FRAGMENT_SHADER_DERIVATIVE_HINT_OES`

mode  
Sets the behavior. The default value is `gl.DONT_CARE`. The possible values are:

-   `gl.FASTEST`: The most efficient behavior should be used.
-   `gl.NICEST`: The most correct or the highest quality option should be used.
-   `gl.DONT_CARE`: There is no preference for this behavior.

### Return value

None.

Examples
--------

The following example hints that the quality of filtering when generating mipmap images should be most efficient instead of best quality.

    gl.hint(gl.GENERATE_MIPMAP_HINT, gl.FASTEST);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'hint' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glHint.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glHint' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`hint`

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

-   [`WebGLRenderingContext.generateMipmap()`](generatemipmap)
-   [`OES_standard_derivatives`](../oes_standard_derivatives)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/hint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/hint</a>
