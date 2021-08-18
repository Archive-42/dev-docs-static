OffscreenCanvas()
=================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `OffscreenCanvas()` constructor returns a newly instantiated [`OffscreenCanvas`](../offscreencanvas) object.

Syntax
------

    new OffscreenCanvas(width, height);

### Parameters

`width`  
The width of the offscreen canvas.

`height`  
The height of the offscreen canvas.

Examples
--------

This example creates a new offscreen canvas using the `OffscreenCanvas()` constructor. We then initialize a [WebGL](../webgl_api) context on it using the [`getContext()`](getcontext) method.

    let offscreen = new OffscreenCanvas(256, 256);
    let gl = offscreen.getContext('webgl');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-offscreencanvas">HTML Living Standard<br />
<span class="small">The definition of 'OffscreenCanvas()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [`OffscreenCanvas`](../offscreencanvas), the interface this constructor belongs to

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas/OffscreenCanvas" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas/OffscreenCanvas</a>
