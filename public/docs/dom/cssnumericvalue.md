# CSSNumericValue

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSNumericValue` interface of the [CSS Typed Object Model API](css_object_model#css_typed_object_model) represents operations that all numeric values can perform.

## Interfaces based on CSSNumericValue

Below is a list of interfaces based on the CSSNumericValue interface.

- <span class="page-not-created">`CSSMathClamp`</span>
- [`CSSMathInvert`](cssmathinvert)
- [`CSSMathMax`](cssmathmax)
- [`CSSMathMin`](cssmathmin)
- [`CSSMathNegate`](cssmathnegate)
- [`CSSMathProduct`](cssmathproduct)
- [`CSSMathSum`](cssmathsum)
- [`CSSMathValue`](cssmathvalue)
- [`CSSNumericArray`](cssnumericarray)
- [`CSSUnitValue`](cssunitvalue)

## Properties

None.

## Methods

### Instance methods

[`CSSNumericValue.add`](cssnumericvalue/add)  
Adds a supplied number to the `CSSNumericValue`.

[`CSSNumericValue.sub`](cssnumericvalue/sub)  
Subtracts a supplied number from the `CSSNumericValue`.

[`CSSNumericValue.mul`](cssnumericvalue/mul)  
Multiplies the `CSSNumericValue` by the supplied value.

[`CSSNumericValue.div`](cssnumericvalue/div)  
Divides the `CSSNumericValue` by the supplied value.

[`CSSNumericValue.min`](cssnumericvalue/min)  
Returns the minimum value passed

[`CSSNumericValue.max`](cssnumericvalue/max)  
Returns the maximum value passed

[`CSSNumericValue.equals`](cssnumericvalue/equals)  
_True_ if all the values are the exact same type and value, in the same order. Otherwise, _false._

[`CSSNumericValue.to`](cssnumericvalue/to)  
Converts `value` into another one with the specified unit.

[`CSSNumericValue.toSum`](cssnumericvalue/tosum)  
Converts an existing `CSSNumericValue` into a [`CSSMathSum`](cssmathsum) object with values of a specified unit.

[`CSSNumericValue.type`](cssnumericvalue/type)  
Returns the type of `CSSNumericValue`, one of `angle`, `flex`, `frequency`, `length`, `resolution`, `percent`, `percentHint`, or `time`.

### Static methods

[`CSSNumericValue.parse`](cssnumericvalue/parse)  
Allows a `CSSNumericValue` to be constructed directly from a string containing CSS.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#numeric-value">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSNumericValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSNumericValue`

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

`add`

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

`min`

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

`sub`

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

`type`

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
- [`CSSPositionValue`](csspositionvalue)
- [`CSSTransformValue`](csstransformvalue)
- [`CSSUnparsedValue`](cssunparsedvalue)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSNumericValue</a>
