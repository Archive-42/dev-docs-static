# CSSNumericValue.to()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `to()` method of the [`CSSNumericValue`](../cssnumericvalue) interface converts a numeric value from one unit to another.

## Syntax

    var cssUnitValue = CSSNumericValue.to(unit);

### Parameters

unit  
The unit to which you want to convert.

### Return value

A [`CSSMathSum`](../cssmathsum).

### Exceptions

SyntaxError  
Indicates that an invalid type was passed to the method.

TypeError  
Indicates that the passed values cannot be summed.

## Examples

    // Prints "0.608542cm"
    console.log(CSS.px("23").to("cm").toString());

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssnumericvalue-to">CSS Typed OM Level 1<br />
<span class="small">The definition of 'to' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`to`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/to" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/to</a>
