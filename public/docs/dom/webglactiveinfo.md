WebGLActiveInfo
===============

The **WebGLActiveInfo** interface is part of the [WebGL API](webgl_api) and represents the information returned by calling the [`WebGLRenderingContext.getActiveAttrib()`](webglrenderingcontext/getactiveattrib) and [`WebGLRenderingContext.getActiveUniform()`](webglrenderingcontext/getactiveuniform) methods.

Properties
----------

[`WebGLActiveInfo.name`](webglactiveinfo/name)  
The read-only name of the requested variable.

[`WebGLActiveInfo.size`](webglactiveinfo/size)  
The read-only size of the requested variable.

[`WebGLActiveInfo.type`](webglactiveinfo/type)  
The read-only type of the requested variable.

Examples
--------

A `WebGLActiveInfo` object is returned by:

-   [`WebGLRenderingContext.getActiveAttrib()`](webglrenderingcontext/getactiveattrib)
-   [`WebGLRenderingContext.getActiveUniform()`](webglrenderingcontext/getactiveuniform) or
-   [`WebGL2RenderingContext.getTransformFeedbackVarying()`](webgl2renderingcontext/gettransformfeedbackvarying)

<!-- -->

    WebGLActiveInfo? getActiveAttrib(WebGLProgram? program, GLuint index);
    WebGLActiveInfo? getActiveUniform(WebGLProgram? program, GLuint index);
    WebGLActiveInfo? getTransformFeedbackVarying(WebGLProgram? program, GLuint index)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.11">WebGL 1.0<br />
<span class="small">The definition of 'WebGLActiveInfo' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLActiveInfo`

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

`name`

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

`size`

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

`type`

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

-   [`WebGLRenderingContext.getActiveAttrib()`](webglrenderingcontext/getactiveattrib)
-   [`WebGLRenderingContext.getActiveUniform()`](webglrenderingcontext/getactiveuniform)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLActiveInfo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLActiveInfo</a>
