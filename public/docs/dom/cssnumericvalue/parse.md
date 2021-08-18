# CSSNumericValue.parse()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `parse()` method of the [`CSSNumericValue`](../cssnumericvalue) interface converts a value string into an object whose members are value and the units.

## Syntax

    var cssNumericValue = CSSNumericValue.parse(cssText);

### Parameters

cssText  
a string containing numeric and unit parts.

### Return value

A [`CSSNumericValue`](../cssnumericvalue).

### Exceptions

SyntaxError  
TBD

## Examples

The following returns a [`CSSUnitValue`](../cssunitvalue) object with a `unit` property equal to `"px"` and a `value` property equal to `42`.

    let numValue = CSSNumericValue.parse("42.0px");

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssnumericvalue-parse">CSS Typed OM Level 1<br />
<span class="small">The definition of 'parse' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`parse`

66

Not exposed to PaintWorklet.

79

Not exposed to PaintWorklet.

No

No

53

Not exposed to PaintWorklet.

No

66

Not exposed to PaintWorklet.

66

Not exposed to PaintWorklet.

No

47

Not exposed to PaintWorklet.

No

9.0

Not exposed to PaintWorklet.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/parse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/parse</a>
