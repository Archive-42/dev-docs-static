# CSSTransformValue()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `CSSTransformValue()` constructor creates a new [`CSSTransformValue`](../csstransformvalue) object which represents a list of individual transform objects.

## Syntax

    var CSSTransformValue = new CSSTransformValue(transforms);

### Parameters

transforms  
A list of [`CSSTransformComponent`](../csstransformcomponent) objects to iterate over.

### Returns

A new [`CSSTransformValue`](../csstransformvalue).

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Raised if transforms is empty.

## Examples

To do

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/">CSS Typed OM Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSTransformValue`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSTransformValue/CSSTransformValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSTransformValue/CSSTransformValue</a>
