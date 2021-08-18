# CSSNumericValue.mul()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `mul()` method of the [`CSSNumericValue`](../cssnumericvalue) interface multiplies the `CSSNumericValue` by the supplied value.

## Syntax

    var cssMathProduct = CSSNumericValue.mul(number);

### Parameters

number  
Either a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) or a [`CSSNumericValue`](../cssnumericvalue).

### Return value

A [`CSSMathProduct`](../cssmathproduct)

### Exceptions

TypeError  
Indicates that an invalid type was passed to the method.

## Examples

    let mathSum = CSS.px("23").mul(CSS.percent("4")).mul(CSS.cm("3")).mul(CSS.in("9"));
    // Prints "calc(23px * 4% * 3cm * 9in)"
    console.log(mathSum.toString());

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssnumericvalue-mul">CSS Typed OM Level 1<br />
<span class="small">The definition of 'mul' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`mul`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/mul" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/mul</a>
