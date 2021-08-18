HTMLCanvasElement.getContext()
==============================

The `HTMLCanvasElement.getContext()` method returns a drawing context on the canvas, or [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) if the context identifier is not supported, or the canvas has already been set to a different context mode.

Later calls to this method on the same canvas element, with the same `contextType` argument, will always return the same drawing context instance as was returned the first time the method was invoked. It is not possible to get a different drawing context object on a given canvas element.

Syntax
------

    var ctx = canvas.getContext(contextType);
    var ctx = canvas.getContext(contextType, contextAttributes);

### Parameters

`contextType`  
Is a [`DOMString`](../domstring) containing the context identifier defining the drawing context associated to the canvas. Possible values are:

-   `"2d"`, leading to the creation of a [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) object representing a two-dimensional rendering context.
-   `"webgl"` (or `"experimental-webgl"`) which will create a [`WebGLRenderingContext`](../webglrenderingcontext) object representing a three-dimensional rendering context. This context is only available on browsers that implement [WebGL](../webgl_api) version 1 (OpenGL ES 2.0).
-   `"webgl2"` which will create a [`WebGL2RenderingContext`](../webgl2renderingcontext) object representing a three-dimensional rendering context. This context is only available on browsers that implement [WebGL](../webgl_api) version 2 (OpenGL ES 3.0). <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
-   `"bitmaprenderer"` which will create an [`ImageBitmapRenderingContext`](../imagebitmaprenderingcontext) which only provides functionality to replace the content of the canvas with a given [`ImageBitmap`](../imagebitmap).

**Note**: The identifier `"experimental-webgl"` is used in new implementations of WebGL. These implementations have either not reached test suite conformance, or the graphics drivers on the platform are not yet stable. The [Khronos Group](https://www.khronos.org/) certifies WebGL implementations under certain [conformance rules](https://www.khronos.org/registry/webgl/sdk/tests/CONFORMANCE_RULES.txt).

`contextAttributes`  
You can use several context attributes when creating your rendering context, for example:

    const gl = canvas.getContext('webgl', {
      antialias: false,
      depth: false
    });

2d context attributes:

-   `alpha`: Boolean that indicates if the canvas contains an alpha channel. If set to `false`, the browser now knows that the backdrop is always opaque, which can speed up drawing of transparent content and images.
-   `desynchronized`: Boolean that hints the user agent to reduce the latency by desynchronizing the canvas paint cycle from the event loop
-   <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> (Gecko only) `willReadFrequently`: Boolean that indicates whether or not a lot of read-back operations are planned. This will force the use of a software (instead of hardware accelerated) 2D canvas and can save memory when calling [`getImageData()`](../canvasrenderingcontext2d/getimagedata) frequently. This option is only available, if the flag `gfx.canvas.willReadFrequently.enable` is set to `true` (which, by default, is only the case for B2G/Firefox OS).
-   <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> (Blink only) `storage`: String that indicates which storage is used ("persistent" by default).

WebGL context attributes:

-   `alpha`: Boolean that indicates if the canvas contains an alpha buffer.
-   `desynchronized`: Boolean that hints the user agent to reduce the latency by desynchronizing the canvas paint cycle from the event loop
-   `antialias`: Boolean that indicates whether or not to perform anti-aliasing.
-   `depth`: Boolean that indicates that the drawing buffer has a depth buffer of at least 16 bits.
-   `failIfMajorPerformanceCaveat`: Boolean that indicates if a context will be created if the system performance is low or if no hardware GPU is available.
-   `powerPreference`: A hint to the user agent indicating what configuration of GPU is suitable for the WebGL context. Possible values are:
    -   `"default"`: Let the user agent decide which GPU configuration is most suitable. This is the default value.
    -   `"high-performance"`: Prioritizes rendering performance over power consumption.
    -   `"low-power"`: Prioritizes power saving over rendering performance.
-   `premultipliedAlpha`: Boolean that indicates that the page compositor will assume the drawing buffer contains colors with pre-multiplied alpha.
-   `preserveDrawingBuffer`: If the value is true the buffers will not be cleared and will preserve their values until cleared or overwritten by the author.
-   `stencil`: Boolean that indicates that the drawing buffer has a stencil buffer of at least 8 bits.

### Return value

A [`RenderingContext`](../renderingcontext) which is either a

-   [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) for `"2d"`,
-   [`WebGLRenderingContext`](../webglrenderingcontext) for `"webgl"` and `"experimental-webgl"`,
-   [`WebGL2RenderingContext`](../webgl2renderingcontext) for `"webgl2"` or
-   [`ImageBitmapRenderingContext`](../imagebitmaprenderingcontext) for `"bitmaprenderer"`.

If the `contextType` doesn't match a possible drawing context, or differs from the first `contextType` requested, `null` is returned.

Examples
--------

Given this [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element:

    <canvas id="canvas" width="300" height="300"></canvas>

You can get a `2d` context of the canvas with the following code:

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');
    console.log(ctx); // CanvasRenderingContext2D { ... }

Now you have the [2D rendering context](../canvasrenderingcontext2d) for a canvas and you can draw within it.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-canvas-getcontext">HTML Living Standard<br />
<span class="small">The definition of 'HTMLCanvasElement.getContext' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since the latest snapshot, <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/semantics-scripting.html#dom-htmlcanvaselement-getcontext">HTML 5.1<br />
<span class="small">The definition of 'HTMLCanvasElement.getContext' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/scripting-1.html#dom-canvas-getcontext">HTML5<br />
<span class="small">The definition of 'HTMLCanvasElement.getContext' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of the <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a> containing the initial definition.</td></tr></tbody></table>

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

1

12

1.5

9

9

3

1

18

4

10.1

1

1.0

`bitmaprenderer_context`

56

≤79

46

No

43

No

No

56

46

43

No

6.0

`desynchronized`

81

ChromeOS and Windows

75

ChromeOS only

71

No

No

No

No

No

No

No

No

No

No

No

`failIfMajorPerformanceCaveat`

Yes

12

41

Yes

Yes

?

No

No

41

?

?

No

`powerPreference`

No

No

63

Firefox respects the GPU hint on macOS only.

No

No

No

No

No

No

No

No

No

`webgl_context`

33

9

79

12

24

3.6

11

15

9

5.1

37

37

33

18

Yes

14

10.1

?

2.0

1.0

`webgl2_context`

56

79

51

25

No

No

No

56

No

No

No

No

No

`2d_alpha_context`

32

≤79

30

No

Yes

No

No

No

30

No

No

No

See also
--------

-   [`CanvasRenderingContext2D.getContextAttributes()`](../canvasrenderingcontext2d/getcontextattributes)
-   [`WebGLRenderingContext.getContextAttributes()`](../webglrenderingcontext/getcontextattributes)
-   The interface defining it, [`HTMLCanvasElement`](../htmlcanvaselement).
-   [`OffscreenCanvas.getContext()`](../offscreencanvas/getcontext)
-   Available rendering contexts: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d), [`WebGLRenderingContext`](../webglrenderingcontext) and [`WebGL2RenderingContext`](../webgl2renderingcontext) and [`ImageBitmapRenderingContext`](../imagebitmaprenderingcontext).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/getContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/getContext</a>
