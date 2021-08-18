# DOMRectReadOnly.fromRect()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `fromRect()` property of the [`DOMRectReadOnly`](../domrectreadonly) interface creates a new `DOMRectReadOnly` object with a given location and dimensions.

## Syntax

    var domRect = DOMRectReadOnly.fromRect(rectangle)

### Parameters

`rectangle` <span class="badge inline optional">Optional</span>  
An object specifying the location and dimensions of a rectangle. All properties default to `0`. The properties are:

- `x`: The coordinate of the left side of the rectangle.
- `y`: The coordinate of the top side of the rectangle.
- `width`: The width of the rectangle.
- `height`: The height of the rectangle.

### Return value

An instance of [`DOMRect`](../domrect).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-domrect-fromrect">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'fromRect()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`fromRect`

61

79

69

No

48

10.1

61

61

No

45

10.3

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/fromRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/fromRect</a>
