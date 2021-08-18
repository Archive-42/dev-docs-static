# CSSScale()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `CSSScale()` constructor creates a new [`CSSScale`](../cssscale) object representing the [scale()](<https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale()>) and [scale3d()](<https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale()>) values of the individual [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) property in CSS.

## Syntax

    var CSSScale = new CSSScale(x,y[,z]);

### Parameters

[`x`](x)  
A value for the x-axis of the [`CSSScale`](../cssscale) object to be constructed. This must either be a double integer or a [`CSSNumericValue`](../cssnumericvalue).

[`y`](y)  
A value for the y-axis of the [`CSSScale`](../cssscale) object to be constructed. This must either be a double integer or a [`CSSNumericValue`](../cssnumericvalue).

[`z`](z)<span class="badge inline optional">Optional</span>  
A value for the z-axis of the [`CSSScale`](../cssscale) object to be constructed. This must either be a double integer or a [`CSSNumericValue`](../cssnumericvalue). If a value is passed for the `z-axis` this is a 3d transform. The value of `is2D` will be set to false.

## Examples

To do

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssscale-cssscale">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSScale' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSScale`

66

79

No

No

53

No

66

66

No

47

No

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSScale/CSSScale" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSScale/CSSScale</a>
