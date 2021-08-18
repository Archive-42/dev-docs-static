ImageBitmapRenderingContext.transferFromImageBitmap()
=====================================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ImageBitmapRenderingContext.transferFromImageBitmap()` method displays the given [`ImageBitmap`](../imagebitmap) in the canvas associated with this rendering context. The ownership of the `ImageBitmap` is transferred to the canvas as well.

This method was previously named `transferImageBitmap()`, but was renamed in a spec change. The old name is being kept as an alias to avoid code breakage.

Syntax
------

    void ImageBitmapRenderingContext.transferFromImageBitmap(bitmap)

### Parameters

`bitmap`  
An [`ImageBitmap`](../imagebitmap) object to transfer.

Examples
--------

### HTML

    <canvas id="htmlCanvas"></canvas>

### JavaScript

    var htmlCanvas = document.getElementById("htmlCanvas").getContext("bitmaprenderer");

    // Draw a WebGL scene offscreen
    var offscreen = new OffscreenCanvas(256, 256);
    var gl = offscreen.getContext("webgl");

    // ... some drawing using the gl context ...

    // Transfer the current frame to the visible canvas
    var bitmap = offscreen.transferToImageBitmap();
    htmlCanvas.transferFromImageBitmap(bitmap);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-imagebitmaprenderingcontext-transferfromimagebitmap">HTML Living Standard<br />
<span class="small">The definition of 'transferFromImageBitmap()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

See also
--------

-   The interface defining this method, [`ImageBitmapRenderingContext`](../imagebitmaprenderingcontext)
-   [`OffscreenCanvas`](../offscreencanvas)
-   [`OffscreenCanvas.transferToImageBitmap()`](../offscreencanvas/transfertoimagebitmap)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmapRenderingContext/transferFromImageBitmap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmapRenderingContext/transferFromImageBitmap</a>
