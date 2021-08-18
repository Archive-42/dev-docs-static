# CSSTranslate()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `CSSTranslate()` constructor creates a new [`CSSTranslate`](../csstranslate) object representing the [translate()](<https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate()>) value of the individual [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) property in CSS.

## Syntax

    var CSSTranslate = new CSSTranslate(x,y[,z]);

### Parameters

[`x`](x)  
A value for the x-axis of the [`CSSTranslate`](../csstranslate) object to be constructed. This must be a [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage).

[`y`](y)  
A value for the y-axis of the [`CSSTranslate`](../csstranslate) object to be constructed. This must be a [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage).

[`z`](z)<span class="badge inline optional">Optional</span>  
A value for the z-axis of the [`CSSTranslate`](../csstranslate) object to be constructed. This must be a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length).

If a value is passed for the `z-axis` this is a 3d transform. The value of `is2D` will be set to false.

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Raised if the value of `CSSTranslate.x` or `CSSTranslate.y` is not a [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage).

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Raised if the value of `CSSTranslate.z` exists but is not a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length).

## Examples

To do

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-csstranslate-csstranslate">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSTranslate' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSTranslate`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSTranslate/CSSTranslate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSTranslate/CSSTranslate</a>
