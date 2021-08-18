# OffscreenCanvas.transferToImageBitmap()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `OffscreenCanvas.transferToImageBitmap()` method creates an [`ImageBitmap`](../imagebitmap) object from the most recently rendered image of the `OffscreenCanvas`.

## Syntax

    ImageBitmap OffscreenCanvas.transferToImageBitmap()

### Return value

An [`ImageBitmap`](../imagebitmap).

## Examples

    var offscreen = new OffscreenCanvas(256, 256);
    var gl = offscreen.getContext("webgl");

    // ... some drawing using the gl context ...

    offscreen.transferToImageBitmap();
    // ImageBitmap { width: 256, height: 256 }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-offscreencanvas-transfertoimagebitmap">HTML Living Standard<br />
<span class="small">The definition of 'OffscreenCanvas.transferToImageBitmap()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

## See also

- The interface defining this method, [`OffscreenCanvas`](../offscreencanvas)
- [`ImageBitmapRenderingContext.transferFromImageBitmap`](../imagebitmaprenderingcontext/transferfromimagebitmap)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas/transferToImageBitmap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas/transferToImageBitmap</a>
