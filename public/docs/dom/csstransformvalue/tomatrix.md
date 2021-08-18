# CSSTransformValue.toMatrix()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `toMatrix()` method of the [`CSSTransformValue`](../csstransformvalue) interface returns a [`DOMMatrix`](../dommatrix) object.

## Syntax

    var matrix = CSSTransformValue.toMatrix();

### Parameters

None

### Return value

A [`DOMMatrix`](../dommatrix) object.

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Raised if any lengths involved in generating the matrix are not compatible units with px (such as relative lengths or percentages).

## Examples

To Do

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-csstransformvalue-tomatrix">CSS Typed OM Level 1<br />
<span class="small">The definition of 'toMatrix()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`toMatrix`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSTransformValue/toMatrix" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSTransformValue/toMatrix</a>
