# CSSUnparsedValue

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSUnparsedValue` interface of the [CSS_Object_Model\#css_typed_object_model](css_object_model#css_typed_object_model) represents property values that reference [custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Variables). It consists of a list of string fragments and variable references.

Custom properties are represented by `CSSUnparsedValue` and [`var()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/var()>) references are represented using [`CSSVariableReferenceValue`](cssvariablereferencevalue).

## Constructor

[`CSSUnparsedValue.CSSUnparsedValue()`](cssunparsedvalue/cssunparsedvalue)  
Creates a new `CSSUnparsedValue` object.

## Properties

[`CSSUnparsedValue.length`](cssunparsedvalue/length)  
Returns the number of items in the `CSSUnparsedValue` object.

## Methods

[`CSSUnparsedValue.entries()`](cssunparsedvalue/entries)  
Returns an array of a given object's own enumerable property `[key, value]` pairs in the same order as that provided by a [`for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in) loop (the difference being that a for-in loop enumerates properties in the prototype chain as well).

[`CSSUnparsedValue.forEach()`](cssunparsedvalue/foreach)  
Executes a provided function once for each element of the `CSSUnparsedValue` object.

[`CSSUnparsedValue.keys()`](cssunparsedvalue/keys)  
Returns a new `Array Iterator` object that contains the keys for each index in the `CSSUnparsedValue` object.

[`CSSUnparsedValue.values()`](cssunparsedvalue/values)  
Returns a new `Array Iterator` object that contains the values for each index in the `CSSUnparsedValue` object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#cssunparsedvalue">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSUnparsedValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSUnparsedValue`

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

`CSSUnparsedSegment`

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

`CSSUnparsedValue`

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

`entries`

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

`forEach`

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

`keys`

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

`length`

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

`values`

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

`@@iterator`

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

## See also

- [`CSSImageValue`](cssimagevalue)
- [`CSSKeywordValue`](csskeywordvalue)
- [`CSSNumericValue`](cssnumericvalue)
- [`CSSPositionValue`](csspositionvalue)
- [`CSSTransformValue`](csstransformvalue)
- [Using the CSS Typed OM](css_typed_om_api/guide)
- [CSS Typed Object Model API](css_typed_om_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSUnparsedValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSUnparsedValue</a>
