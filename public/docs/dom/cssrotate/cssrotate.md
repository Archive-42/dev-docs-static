# CSSRotate()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `CSSRotate()` constructor creates a new [`CSSRotate`](../cssrotate) object representing the [rotate()](<https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate()>) value of the individual [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) property in CSS.

## Syntax

    var CSSRotate = new CSSRotate(x,y,z,angle);

### Parameters

[`x`](x)  
A value for the x-axis of the [`CSSRotate`](../cssrotate) object to be constructed. This must either be a double integer or a [`CSSNumericValue`](../cssnumericvalue).

[`y`](y)  
A value for the y-axis of the [`CSSRotate`](../cssrotate) object to be constructed. This must either be a double integer or a [`CSSNumericValue`](../cssnumericvalue).

[`z`](z)  
A value for the z-axis of the [`CSSRotate`](../cssrotate) object to be constructed. This must either be a double integer or a [`CSSNumericValue`](../cssnumericvalue).

[`angle`](angle)  
A value for the angle of the [`CSSRotate`](../cssrotate) object to be constructed. This must be a [`CSSNumericValue`](../cssnumericvalue).

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Raised if the value of `CSSRotate.angle` is not an [&lt;angle&gt;](https://developer.mozilla.org/en-US/docs/Web/CSS/angle) value or `CSSRotate.x`, `CSSRotate.y`, `CSSRotate.z` are not [&lt;number&gt;](https://developer.mozilla.org/en-US/docs/Web/CSS/number) values.

## Examples

To do

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#cssrotate">CSS Typed OM Level 1<br />
<span class="small">The definition of 'cssrotate' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSRotate`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSRotate/CSSRotate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSRotate/CSSRotate</a>
