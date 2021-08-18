# ImageBitmapRenderingContext

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ImageBitmapRenderingContext` interface is a canvas rendering context that provides the functionality to replace the canvas's contents with the given [`ImageBitmap`](imagebitmap). Its context id (the first argument to [`HTMLCanvasElement.getContext()`](htmlcanvaselement/getcontext) or [`OffscreenCanvas.getContext()`](offscreencanvas/getcontext)) is `"bitmaprenderer"`.

This interface is available in both the window and the [worker](web_workers_api) context.

## Methods

[`ImageBitmapRenderingContext.transferFromImageBitmap()`](imagebitmaprenderingcontext/transferfromimagebitmap)  
Displays the given `ImageBitmap` in the canvas associated with this rendering context. Ownership of the `ImageBitmap` is transferred to the canvas. This was previously named `transferImageBitmap()`, but was renamed in a spec change. The old name is being kept as an alias to avoid code breakage.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/canvas.html#the-imagebitmaprenderingcontext-interface">HTML Living Standard<br />
<span class="small">The definition of 'ImageBitmapRenderingContext' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`ImageBitmapRenderingContext`

56

≤79

46

No

43

No

56

56

46

43

No

6.0

`canvas`

56

79

No

No

43

No

56

56

No

43

No

6.0

`transferFromImageBitmap`

56

≤79

52

46-52

No

43

No

56

56

52

46-52

43

No

6.0

## See also

- [`OffScreenCanvas`](offscreencanvas)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmapRenderingContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmapRenderingContext</a>
