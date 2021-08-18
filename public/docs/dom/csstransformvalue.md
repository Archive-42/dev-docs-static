# CSSTransformValue

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `CSSTransformValue` interface of the [CSS_Object_Model\#css_typed_object_model](css_object_model#css_typed_object_model) represents `transform-list` values as used by the CSS [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) property.

## Interfaces based on CSSTransformValue

Below is a list of interfaces based on the `CSSTransformValue` interface.

- [`CSSTranslate`](csstranslate)
- [`CSSRotate`](cssrotate)
- [`CSSScale`](cssscale)
- [`CSSSkew`](cssskew)
- [`CSSSkewX`](cssskewx)
- [`CSSSkewY`](cssskewy)
- [`CSSPerspective`](cssperspective)
- [`CSSMatrixComponent`](cssmatrixcomponent)

## Constructor

[`CSSTransformValue.CSSTransformValue()`](csstransformvalue/csstransformvalue)  
Creates a new `CSSTransformValue` object.

## Properties

[`CSSTransformValue.length`](csstransformvalue/length) <span class="badge inline readonly">Read only </span>  
Returns how many transform components are contained within the `CSSTransformValue`.

[`CSSTransformValue.is2D`](csstransformvalue/is2d) <span class="badge inline readonly">Read only </span>  
Returns a boolean indicating whether the transform is 2D or 3D.

## Methods

_Inherits methods from its ancestor [`CSSStyleValue`](cssstylevalue)._

[`CSSTransformValue.toMatrix()`](csstransformvalue/tomatrix)  
Returns a new [`DOMMatrix`](dommatrix) object.

[`CSSUnparsedValue.entries()`](cssunparsedvalue/entries)  
Returns an array of a given object's own enumerable property `[key, value]` pairs in the same order as that provided by a [`for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in) loop (the difference being that a for-in loop enumerates properties in the prototype chain as well).

[`CSSUnparsedValue.forEach()`](cssunparsedvalue/foreach)  
Executes a provided function once for each element of the `CSSTransformValue` object.

[`CSSUnparsedValue.keys()`](cssunparsedvalue/keys)  
Returns a new `Array Iterator` object that contains the keys for each index in the `CSSTransformValue` object.

[`CSSUnparsedValue.values()`](cssunparsedvalue/values)  
Returns a new `Array Iterator` object that contains the values for each index in the `CSSTransformValue` object.

## Examples

To Do.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#csstransformvalue">CSS Typed OM Level 1<br />
<span class="small">The definition of 'cssTransformValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSTransformValue`

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

`CSSTransformValue`

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

`is2D`

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

`toMatrix`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSTransformValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSTransformValue</a>
