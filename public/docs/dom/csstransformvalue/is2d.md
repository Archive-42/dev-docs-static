# CSSTransformValue.is2D

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The read-only `is2D` property of the [`CSSTransformValue`](../csstransformvalue) interface returns whether the transform is 2D or 3D.

In the case of the `CSSTransformValue` this property returns true unless any of the individual functions return false for `Is2D`, in which case it returns false.

## Syntax

    var is2D = CSSTransformValue.is2D;

### Return value

A boolean. True indicates that the transform is a 2D transform, false that it is a 3D transform.

## Examples

To Do

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-csstransformvalue-is2d">CSS Typed OM Level 1<br />
<span class="small">The definition of 'is2D' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`is2D`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSTransformValue/is2D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSTransformValue/is2D</a>
