# OffscreenCanvas.width

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `width` property returns and sets the width of an [`OffscreenCanvas`](../offscreencanvas) object.

## Syntax

    var pxl = offscreen.width;
    offscreen.width = pxl;

## Examples

Creating a new offscreen canvas and returning or setting the width of the offscreen canvas:

    var offscreen = new OffscreenCanvas(256, 256);
    offscreen.width; // 256
    offscreen.width = 512;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-offscreencanvas-width">HTML Living Standard<br />
<span class="small">The definition of 'OffscreenCanvas.width' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

- [`OffscreenCanvas`](../offscreencanvas), the interface this property belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas/width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas/width</a>
