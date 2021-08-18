# CSSNumericValue.div()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `div()` method of the [`CSSNumericValue`](../cssnumericvalue) interface divides the `CSSNumericValue` by the supplied value.

## Syntax

    var cssNumericValue = CSSNumericValue.div(number);

### Parameters

number  
Either a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) or a [`CSSNumericValue`](../cssnumericvalue).

### Return value

A [`CSSMathProduct`](../cssmathproduct).

### Exceptions

TypeError  
Indicates that an invalid type was passed to the method.

## Examples

    let mathProduct = CSS.px("24").div(CSS.percent("4"));
    // Prints "calc(24px / 4%)"
    mathProduct.toString();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssnumericvalue-div">CSS Typed OM Level 1<br />
<span class="small">The definition of 'div' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`div`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/div" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/div</a>
