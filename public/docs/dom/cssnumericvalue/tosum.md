# CSSNumericValue.toSum()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `toSum()` method of the [`CSSNumericValue`](../cssnumericvalue) interface converts the object's value to a [`CSSMathSum`](../cssmathsum) object to values of the specified unit.

## Syntax

    var cssMathSum = CSSNumericValue.toSum(units);

### Parameters

units  
The units to convert to.

### Return value

A [`CSSNumericValue`](../cssnumericvalue).

### Exceptions

SyntaxError  
undefined

TypeError  
Indicates that an invalid type was passed to the method.

## Examples

    let v = CSS.px("23").add(CSS.percent("4")).add(CSS.cm("3")).add(CSS.in("9"));
    v.toString() // => "calc(23px + 4% + 3cm + 9in)"
    v.toSum("px", "percent").toString() // => "calc(1000.39px + 4%)"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssnumericvalue-tosum">CSS Typed OM Level 1<br />
<span class="small">The definition of 'toSum' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`toSum`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/toSum" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/toSum</a>
