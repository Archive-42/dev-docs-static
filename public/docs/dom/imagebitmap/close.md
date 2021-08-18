# ImageBitmap.close()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` ImageBitmap``.close() ` method disposes of all graphical resources associated with an `ImageBitmap`.

## Syntax

    void ImageBitmap.close()

## Examples

    var offscreen = new OffscreenCanvas(256, 256);
    var gl = offscreen.getContext('webgl');

    // ... some drawing using the gl context ...

    var bitmap = offscreen.transferToImageBitmap();
    // ImageBitmap { width: 256, height: 256 }

    bitmap.close();
    // ImageBitmap { width: 0, height: 0 } -- disposed

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#dom-imagebitmap-close">HTML Living Standard<br />
<span class="small">The definition of 'close()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`close`

52

79

46

No

37

No

52

52

46

37

No

6.0

## See also

- The interface defining this method, [`ImageBitmap`](../imagebitmap).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmap/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmap/close</a>
