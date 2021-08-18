# CSSNumericValue.max()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `max()` method of the [`CSSNumericValue`](../cssnumericvalue) interface returns the highest value from among the values passed. The passed values must be of the same type.

## Syntax

    var cssUnitValue = CSSNumericValue.man(number1 ... numbern);

### Parameters

number  
Either a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) or a [`CSSNumericValue`](../cssnumericvalue).

### Return value

A [`CSSUnitValue`](../cssunitvalue).

### Exceptions

TypeError  
Indicates that an invalid type was passed to the method.

## Examples

As stated earlier, all passed values must be of the same type and value. Some of the following examples illustrate what happens when they are not.

    // Prints "2cm"
    console.log(CSS.cm("1").max(CSS.cm("2")).toString());

    // Prints "max(1cm, 0.393701in)"
    console.log(CSS.cm("1").max(CSS.in("0.393701")).toString());

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssnumericvalue-max">CSS Typed OM Level 1<br />
<span class="small">The definition of 'max' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`max`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/max" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue/max</a>
