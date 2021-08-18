# CSS Typed Object Model API

The CSS Typed Object Model API simplifies CSS property manipulation by exposing CSS values as typed JavaScript objects rather than strings. This not only simplifies CSS manipulation, but also lessens the negative impact on performance as compared to [`ElementCSSInlineStyle.style`](elementcssinlinestyle/style).

Generally, CSS values can be read and written in JavaScript as strings, which can be slow and cumbersome. CSS Typed Object Model API provides interfaces to interact with underlying values, by representing them with specialized JS objects that can be manipulated and understood more easily and more reliably than string parsing and concatenation. This is easier for authors (for example, numeric values are reflected with actual JS numbers, and have unit-aware mathematical operations defined for them). It is also generally faster, as values can be directly manipulated and then cheaply translated back into underlying values without having to both build and parse strings of CSS.

CSS Typed OM both allows for the performant manipulation of values assigned to CSS properties while enabling maintainable code that is both more understandable and easier to write.

## Interfaces

### `CSSStyleValue`

The [`CSSStyleValue`](cssstylevalue) interface of the CSS Typed Object Model API is the base class of all CSS values accessible through the Typed OM API. An instance of this class may be used anywhere a string is expected.

[`CSSStyleValue.parse(property, cssText)`](cssstylevalue/parse)  
The parse() method of the CSSStyleValue interface allows a CSSNumericValue to be constructed from a CSS string. It sets a specific CSS property to the specified values and returns the first value as a CSSStyleValue object.

[`CSSStyleValue.parseAll()`](cssstylevalue/parseall)  
The parseAll() method of the CSSStyleValue interface sets all occurrences of a specific CSS property to the specified value and returns an array of CSSStyleValue objects, each containing one of the supplied values.

### `StylePropertyMap`

The [`StylePropertyMap`](stylepropertymap) interface of the CSS Typed Object Model API provides a representation of a CSS declaration block that is an alternative to CSSStyleDeclaration.

[`StylePropertyMap.set()`](stylepropertymap/set)  
Method of StylePropertyMap interface that changes the CSS declaration with the given property to the value given.

[`StylePropertyMap.append()`](stylepropertymap/append)  
Method that adds a new CSS declaration to the StylePropertyMap with the given property and value.

[`StylePropertyMap.delete()`](stylepropertymap/delete)  
Method that removes the CSS declaration with the given property from the StylePropertyMap.

[`StylePropertyMap.clear()`](stylepropertymap/clear)  
Method that removes all declarations in the StylePropertyMap.

### `CSSUnparsedValue`

The [`CSSUnparsedValue`](cssunparsedvalue) interface of the CSS Typed Object Model API represents property values that reference custom properties. It consists of a list of string fragments and variable references.

[`CSSUnparsedValue.CSSUnparsedValue()`](cssunparsedvalue/cssunparsedvalue) constructor  
Creates a new CSSUnparsedValue object which represents property values that reference custom properties.

[`CSSUnparsedValue.entries()`](cssunparsedvalue/entries)  
Method returning an array of a given object's own enumerable property \[key, value\] pairs in the same order as that provided by a for...in loop (the difference being that a for-in loop enumerates properties in the prototype chain as well).

[`CSSUnparsedValue.forEach()`](cssunparsedvalue/foreach)  
Method executing a provided function once for each element of the CSSUnparsedValue.

[`CSSUnparsedValue.keys()`](cssunparsedvalue/keys)  
Method returning a new Array Iterator object that contains the keys for each index in the array.

### `CSSKeywordValue` Serialization

The [`CSSKeywordValue`](csskeywordvalue) interface of the CSS Typed Object Model API creates an object to represent CSS keywords and other identifiers.

[`CSSKeywordValue.CSSKeywordValue()`](csskeywordvalue/csskeywordvalue) constructor  
Constructor creates a new [`CSSKeywordValue.CSSKeywordValue()`](csskeywordvalue/csskeywordvalue) object which represents CSS keywords and other identifiers.

[`CSSKeywordValue.value()`](csskeywordvalue/value)  
Property of the CSSKeywordValue interface returning or setting the value of the CSSKeywordValue.

## CSSStyleValue Interfaces

CSSStyleValue is the base class through which all CSS values are expressed. Subclasses include:

[`CSSImageValue`](cssimagevalue) objects  
An interface representing values for properties that take an image, for example `background-image`, `list-style-image`, or `border-image-source`.

[`CSSKeywordValue`](csskeywordvalue)  
An interface which creates an object to represent CSS keywords and other identifiers. When used where a string is expected, it will return the value of CSSKeyword.value.

[`CSSMathValue`](cssmathvalue)  
A tree of subclasses representing numeric values that are more complicated than a single value and unit, including:

- [`CSSMathInvert`](cssmathinvert) - represents a CSS [`calc()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/calc()>) value used as `calc(1 / <value>)`.
- [`CSSMathMax`](cssmathmax) - represents the CSS [`max()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/max()>) function.
- [`CSSMathMin`](cssmathmin) - represents the CSS [`min()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/min()>) function.
- [`CSSMathNegate`](cssmathnegate) - negates the value passed into it.
- [`CSSMathProduct`](cssmathproduct) - represents the result obtained by calling [`add()`](cssnumericvalue/add), [`sub()`](cssnumericvalue/sub), or [`toSum()`](cssnumericvalue/tosum) on [`CSSNumericValue`](cssnumericvalue).
- [`CSSMathSum`](cssmathsum) - represents the result obtained by calling [`add()`](cssnumericvalue/add), [`sub()`](cssnumericvalue/sub), or [`toSum()`](cssnumericvalue/tosum) on [`CSSNumericValue`](cssnumericvalue).

[`CSSNumericValue`](cssnumericvalue)  
An interface representing operations that all numeric values can perform, including:

- [`CSSNumericValue.add`](cssnumericvalue/add) - Adds supplied numbers to the `CSSNumericValue`.
- [`CSSNumericValue.sub`](cssnumericvalue/sub) - Subtracts supplied numbers to the `CSSNumericValue`.
- [`CSSNumericValue.mul`](cssnumericvalue/mul) - Multiplies supplied numbers to the `CSSNumericValue`.
- [`CSSNumericValue.div`](cssnumericvalue/div) - Divides a supplied number by other numbers, throwing an error if 0.
- [`CSSNumericValue.min`](cssnumericvalue/min) - Returns the minimum value passed
- [`CSSNumericValue.max`](cssnumericvalue/max) - Returns the maximum value passed
- [`CSSNumericValue.equals`](cssnumericvalue/equals) - Returns true if all the values are the exact same type and value, in the same order. Otherwise, false
- [`CSSNumericValue.to`](cssnumericvalue/to) - Converts `value` into another one with the specified unit.
- [`CSSNumericValue.toSum`](cssnumericvalue/tosum)
- [`CSSNumericValue.type`](cssnumericvalue/type)
- [`CSSNumericValue.parse`](cssnumericvalue/parse) - Returns a number parsed from a CSS string

[`CSSPositionValue`](csspositionvalue)  
Represents values for properties that take a position, for example object-position.

[`CSSTransformValue`](csstransformvalue)  
An interface representing a list of `transform` list values. They "contain" one or more [`CSSTransformComponent`](csstransformcomponent)s, which represent individual `transform` function values.

[`CSSUnitValue`](cssunitvalue)  
An interface representing numeric values that can be represented as a single unit, or a named number and percentage.

[`CSSUnparsedValue`](cssunparsedvalue)  
Represents property values that reference [custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*). It consists of a list of string fragments and variable references.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/">CSS Typed OM Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

- [CSSStyleValue](cssstylevalue#browser_compatibility)
- [StylePropertyMap](stylepropertymap#browser_compatibility)
- [CSSUnparsedValue](cssunparsedvalue#browser_compatibility)
- [CSSKeywordValue](csskeywordvalue#browser_compatibility)

## See also

- [CSS Painting API](css_painting_api)
- [Using the CSS Typed Object Model](css_typed_om_api/guide)
- [CSS Houdini](https://developer.mozilla.org/en-US/docs/Web/Houdini)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS_Typed_OM_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS_Typed_OM_API</a>
