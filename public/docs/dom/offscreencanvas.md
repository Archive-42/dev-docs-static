# OffscreenCanvas

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `OffscreenCanvas` interface provides a canvas that can be rendered off screen. It is available in both the window and [worker](web_workers_api) contexts.

**Note:** This feature is available in [Web Workers](web_workers_api).

## Constructors

[`OffscreenCanvas()`](offscreencanvas/offscreencanvas)  
`OffscreenCanvas` constructor. Creates a new `OffscreenCanvas` object.

## Properties

[`OffscreenCanvas.height`](offscreencanvas/height)  
The height of the offscreen canvas.

[`OffscreenCanvas.width`](offscreencanvas/width)  
The width of the offscreen canvas.

## Methods

[`OffscreenCanvas.getContext()`](offscreencanvas/getcontext)  
Returns a rendering context for the offscreen canvas.

[`OffscreenCanvas.convertToBlob()`](offscreencanvas/converttoblob)  
Creates a [`Blob`](blob) object representing the image contained in the canvas.

[`OffscreenCanvas.transferToImageBitmap()`](offscreencanvas/transfertoimagebitmap)  
Creates an [`ImageBitmap`](imagebitmap) object from the most recently rendered image of the `OffscreenCanvas`.

## Examples

### Synchronous display of frames produced by an `OffscreenCanvas`

One way to use the `OffscreenCanvas` API, is to use a [`RenderingContext`](renderingcontext) that has been obtained from an `OffscreenCanvas` object to generate new frames. Once a new frame has finished rendering in this context, the [`transferToImageBitmap()`](offscreencanvas/transfertoimagebitmap) method can be called to save the most recent rendered image. This method returns an [`ImageBitmap`](imagebitmap) object, which can be used in a variety of Web APIs and also in a second canvas without creating a transfer copy.

To display the `ImageBitmap`, you can use a [`ImageBitmapRenderingContext`](imagebitmaprenderingcontext) context, which can be created by calling `canvas.getContext("bitmaprenderer")` on a (visible) canvas element. This context only provides functionality to replace the canvas's contents with the given `ImageBitmap`. A call to [`ImageBitmapRenderingContext.transferFromImageBitmap()`](imagebitmaprenderingcontext/transferfromimagebitmap) with the previously rendered and saved `ImageBitmap` from the OffscreenCanvas, will display the `ImageBitmap` on the canvas and transfer its ownership to the canvas. A single `OffscreenCanvas` may transfer frames into an arbitrary number of other `ImageBitmapRenderingContext` objects.

Given these two [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) elements

    <canvas id="one"></canvas>
    <canvas id="two"></canvas>

the following code will provide the rendering using an `OffscreenCanvas` as described above.

    var one = document.getElementById("one").getContext("bitmaprenderer");
    var two = document.getElementById("two").getContext("bitmaprenderer");

    var offscreen = new OffscreenCanvas(256, 256);
    var gl = offscreen.getContext('webgl');

    // ... some drawing for the first canvas using the gl context ...

    // Commit rendering to the first canvas
    var bitmapOne = offscreen.transferToImageBitmap();
    one.transferFromImageBitmap(bitmapOne);

    // ... some more drawing for the second canvas using the gl context ...

    // Commit rendering to the second canvas
    var bitmapTwo = offscreen.transferToImageBitmap();
    two.transferFromImageBitmap(bitmapTwo);

### Asynchronous display of frames produced by an `OffscreenCanvas`

Another way to use the `OffscreenCanvas` API, is to call [`transferControlToOffscreen()`](htmlcanvaselement/transfercontroltooffscreen) on a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element, either on a [worker](web_workers_api) or the main thread, which will return an `OffscreenCanvas` object from an [`HTMLCanvasElement`](htmlcanvaselement) object from the main thread. Calling [`getContext()`](offscreencanvas/getcontext) will then obtain a `RenderingContext` from that `OffscreenCanvas`.

main.js (main thread code):

    var htmlCanvas = document.getElementById("canvas");
    var offscreen = htmlCanvas.transferControlToOffscreen();

    var worker = new Worker("offscreencanvas.js");
    worker.postMessage({canvas: offscreen}, [offscreen]);

offscreencanvas.js (worker code):

    onmessage = function(evt) {
      var canvas = evt.data.canvas;
      var gl = canvas.getContext("webgl");

      // ... some drawing using the gl context ...
    };

You can also use requestAnimationFrame in workers

    onmessage = function(evt) {
      const canvas = evt.data.canvas;
      const gl = canvas.getContext("webgl");

      function render(time) {
        // ... some drawing using the gl context ...
        requestAnimationFrame(render);
      }
      requestAnimationFrame(render);
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#the-offscreencanvas-interface">HTML Living Standard<br />
<span class="small">The definition of 'OffscreenCanvas' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

`OffscreenCanvas`

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

`OffscreenCanvas`

69

≤79

46

See [bug 1390089](https://bugzil.la/1390089).

No

56

No

No

69

46

See [bug 1390089](https://bugzil.la/1390089).

Yes

No

10.0

`convertToBlob`

69

≤79

46

See [bug 1390089](https://bugzil.la/1390089).

No

56

No

No

69

46

See [bug 1390089](https://bugzil.la/1390089).

48

No

10.0

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

`height`

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

`transferToImageBitmap`

69

≤79

46

See [bug 1390089](https://bugzil.la/1390089).

No

56

No

No

69

46

See [bug 1390089](https://bugzil.la/1390089).

48

No

10.0

`width`

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

## See also

- [WebGL Off the Main Thread – Mozilla Hacks](https://hacks.mozilla.org/2016/01/webgl-off-the-main-thread/)
- [`CanvasRenderingContext2D`](canvasrenderingcontext2d)
- [`ImageBitmap`](imagebitmap)
- [`ImageBitmapRenderingContext`](imagebitmaprenderingcontext)
- [`HTMLCanvasElement.transferControlToOffscreen()`](htmlcanvaselement/transfercontroltooffscreen)
- [`WebGLRenderingContext.commit()`](webglrenderingcontext/commit)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas</a>
