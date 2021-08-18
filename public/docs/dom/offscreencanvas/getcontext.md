OffscreenCanvas.getContext()
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `OffscreenCanvas.getContext()` method returns a drawing context for an offscreen canvas, or [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) if the context identifier is not supported.

**Note**: This API is currently implemented for [WebGL1](../webglrenderingcontext) and [WebGL2](../webgl2renderingcontext) contexts only. See [bug 801176](https://bugzilla.mozilla.org/show_bug.cgi?id=801176) for [Canvas 2D API](../canvas_api) support from workers.

Syntax
------

    offscreen.getContext(contextType, contextAttributes);

### Parameters

`contextType`  
Is a [`DOMString`](../domstring) containing the context identifier defining the drawing context associated to the canvas. Possible values are:

-   `"2d"` creates a [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) object representing a two-dimensional rendering context.
-   `"webgl"` creates a [`WebGLRenderingContext`](../webglrenderingcontext) object representing a three-dimensional rendering context. This context is only available on browsers that implement [WebGL](../webgl_api) version 1 (OpenGL ES 2.0).
-   `"webgl2"` creates a [`WebGL2RenderingContext`](../webgl2renderingcontext) object representing a three-dimensional rendering context. This context is only available on browsers that implement [WebGL](../webgl_api) version 2 (OpenGL ES 3.0). <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
-   `"bitmaprenderer"` creates a [`ImageBitmapRenderingContext`](../imagebitmaprenderingcontext) which only provides functionality to replace the content of the canvas with a given [`ImageBitmap`](../imagebitmap).

Note: The identifiers `"experimental-webgl"` or `"experimental-webgl2"` are also used in implementations of WebGL. These implementations have not reached test suite conformance, or the graphic drivers situation on the platform is not yet stable. The [Khronos Group](https://www.khronos.org/) certifies WebGL implementations under certain [conformance rules](https://www.khronos.org/registry/webgl/sdk/tests/CONFORMANCE_RULES.txt).

`contextAttributes`  
You can use several context attributes when creating your rendering context, for example:

    offscreen.getContext("webgl",
                     { antialias: false,
                       depth: false });

2d context attributes:

-   `alpha`: Boolean that indicates if the canvas contains an alpha channel. If set to `false`, the browser now knows that the backdrop is always opaque, which can speed up drawing of transparent content and images then.
-   <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> (Gecko only) `willReadFrequently`: Boolean that indicates whether or not a lot of read-back operations are planned. This will force the use of a software (instead of hardware accelerated) 2D canvas and can save memory when calling [`getImageData()`](../canvasrenderingcontext2d/getimagedata) frequently. This option is only available, if the flag `gfx.canvas.willReadFrequently.enable` is set to `true` (which, by default, is only the case for B2G/Firefox OS).
-   <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> (Blink only) `storage`: String that indicates which storage is used ("persistent" by default).

WebGL context attributes:

-   `alpha`: Boolean that indicates if the canvas contains an alpha buffer.
-   `depth`: Boolean that indicates that the drawing buffer has a depth buffer of at least 16 bits.
-   `stencil`: Boolean that indicates that the drawing buffer has a stencil buffer of at least 8 bits.
-   `antialias`: Boolean that indicates whether or not to perform anti-aliasing.
-   `premultipliedAlpha`: Boolean that indicates that the page compositor will assume the drawing buffer contains colors with pre-multiplied alpha.
-   `preserveDrawingBuffer`: If the value is true the buffers will not be cleared and will preserve their values until cleared or overwritten by the author.
-   `failIfMajorPerformanceCaveat`: Boolean that indicates if a context will be created if the system performance is low.

### Return value

A [`RenderingContext`](../renderingcontext) which is either a

-   [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) for `"2d"`,
-   [`WebGLRenderingContext`](../webglrenderingcontext) for `"webgl"` and `"experimental-webgl"`,
-   [`WebGL2RenderingContext`](../webgl2renderingcontext) for `"webgl2"` and `"experimental-webgl2"` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>, or
-   [`ImageBitmapRenderingContext`](../imagebitmaprenderingcontext) for `"bitmaprenderer"`.

If the `contextType` doesn't match a possible drawing context, `null` is returned.

Examples
--------

    var offscreen = new OffscreenCanvas(256, 256);
    var gl = offscreen.getContext("webgl");

    gl; // WebGLRenderingContext
    gl.canvas; // OffscreenCanvas

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-offscreencanvas-getcontext">HTML Living Standard<br />
<span class="small">The definition of 'OffscreenCanvas.getContext()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`getContext`

69

≤79

44

See [bug 1390089](https://bugzil.la/1390089).

No

56

No

No

69

44

See [bug 1390089](https://bugzil.la/1390089).

48

No

10.0

`bitmaprenderer_context`

76

≤79

46

See [bug 1390089](https://bugzil.la/1390089).

No

63

No

No

76

46

See [bug 1390089](https://bugzil.la/1390089).

54

No

12.0

`webgl_context`

69

≤79

44

See [bug 1390089](https://bugzil.la/1390089).

No

56

No

No

69

44

See [bug 1390089](https://bugzil.la/1390089).

48

No

10.0

`webgl2_context`

69

≤79

44

See [bug 1390089](https://bugzil.la/1390089).

No

56

No

No

69

44

See [bug 1390089](https://bugzil.la/1390089).

48

No

10.0

`2d_context`

69

≤79

No

No

56

No

No

69

No

48

No

10.0

See also
--------

-   The interface defining this method: [`OffscreenCanvas`](../offscreencanvas)
-   [`HTMLCanvasElement.getContext()`](../htmlcanvaselement/getcontext)
-   Available rendering contexts: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d), [`WebGLRenderingContext`](../webglrenderingcontext), [`WebGL2RenderingContext`](../webgl2renderingcontext), and [`ImageBitmapRenderingContext`](../imagebitmaprenderingcontext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas/getContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas/getContext</a>
