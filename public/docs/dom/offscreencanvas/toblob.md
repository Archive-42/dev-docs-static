# OffscreenCanvas.convertToBlob()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `OffscreenCanvas.convertToBlob()` method creates a [`Blob`](../blob) object representing the image contained in the canvas.

## Syntax

    Promise<Blob> OffscreenCanvas.convertToBlob(options);

### Parameters

`options` <span class="badge inline optional">Optional</span>  
You can specify several options when converting your [`OffscreenCanvas`](../offscreencanvas) object into a [`Blob`](../blob) object, for example:

    const blob = offscreenCanvas.convertToBlob({
      type: "image/jpeg",
      quality: 0.95
    });

options:

- `type`: A [`DOMString`](../domstring) indicating the image format. The default type is `image/png`.
- `quality`: A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) between `0` and `1` indicating image quality if the `type` option is `image/jpeg` or `image/webp`. If this argument is anything else, the default value for image quality is used. Other arguments are ignored.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returning a [`Blob`](../blob) object representing the image contained in the canvas.

## Examples

    var offscreen = new OffscreenCanvas(256, 256);
    var gl = offscreen.getContext("webgl");

    // ... some drawing using the gl context ...

    offscreen.convertToBlob().then(function(blob) {
      console.log(blob);
    });

    // Blob { size: 334, type: "image/png" }

## Specifications

Currently drafted as a proposal: [OffscreenCanvas](https://wiki.whatwg.org/wiki/OffscreenCanvas).

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

`toBlob`

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

- The interface defining this method, [`OffscreenCanvas`](../offscreencanvas).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas/toBlob" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas/toBlob</a>
