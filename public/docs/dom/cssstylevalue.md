# CSSStyleValue

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSStyleValue` interface of the [CSS Typed Object Model API](css_object_model#css_typed_object_model) is the base class of all CSS values accessible through the Typed OM API. An instance of this class may be used anywhere a string is expected.

## Interfaces based on CSSStyleValue

Below is a list of interfaces based on the `CSSStyleValue` interface.

- [`CSSImageValue`](cssimagevalue)
- [`CSSKeywordValue`](csskeywordvalue)
- [`CSSNumericValue`](cssnumericvalue)
- [`CSSPositionValue`](csspositionvalue)
- [`CSSTransformValue`](csstransformvalue)
- [`CSSUnparsedValue`](cssunparsedvalue)

## Methods

[`CSSStyleValue.parse()`](cssstylevalue/parse)  
Sets a specific CSS property to the specified values and returns the first value as a [`CSSStyleValue`](cssstylevalue) object.

[`CSSStyleValue.parseAll()`](cssstylevalue/parseall)  
Sets all occurrences of a specific CSS property to the specified valueand returns an array of [`CSSStyleValue`](cssstylevalue) objects, each containing one of the supplied values.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#stylevalue-objects">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSStyleValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSStyleValue`

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

`parse`

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

`parseAll`

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

`toString`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleValue</a>
