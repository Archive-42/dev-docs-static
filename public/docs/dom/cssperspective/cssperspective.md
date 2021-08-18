# CSSPerspective()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `CSSPerspective()` constructor creates a new [`CSSPerspective`](../cssperspective) object representing the [perspective()](<https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/perspective()>) value of the individual [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) property in CSS.

## Syntax

    var CSSPerspective = new CSSPerspective(length);

### Parameters

[`length`](length)  
A value for the distance from z=0 of the [`CSSPerspective`](../cssperspective) object to be constructed. This must be a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length).

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Raised if the value of `CSSPerspective.length` exists but is not a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length).

## Examples

To do

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#cssperspective">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSPerspective' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSPerspective`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPerspective/CSSPerspective" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPerspective/CSSPerspective</a>
