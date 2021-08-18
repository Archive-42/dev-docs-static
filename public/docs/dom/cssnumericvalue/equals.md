# CSSNumericValue.equals()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `equals()` method of the [`CSSNumericValue`](../cssnumericvalue) interface returns a boolean indicating whether the passed value are strictly equal. To return a value of `true`, all passed values must be of the same type and value and must be in the same order. This allows structural equality to be tested quickly.

## Syntax

    var boolean = CSSNumericValue.equals(number);

### Parameters

number  
Either a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) or a [`CSSNumericValue`](../cssnumericvalue).

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

### Exceptions

None.

## Examples

As stated earlier, all passed values must be of the same type and value and must be in the same order. Some of the following examples illustrate what happens when they are not.

    let cssMathSum = new CSSMathSum(CSS.px(1), CSS.px(2));
    let matchingCssMathSum = new CSSMathSum(CSS.px(1), CSS.px(2));
    // Prints true
    console.log(cssMathSum.equals(matchingCssMathSum));

    let otherCssMathSum = CSSMathSum(CSS.px(2), CSS.px(1));
    // Prints false
    console.log(cssMathSum.equals(otherCssMathSum));

    // Also prints false
    console.log(CSS.cm("1").equal(CSS.in("0.393701")));

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssnumericvalue-equals">CSS Typed OM Level 1<br />
<span class="small">The definition of 'equals' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`equals`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/equals" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/equals</a>
