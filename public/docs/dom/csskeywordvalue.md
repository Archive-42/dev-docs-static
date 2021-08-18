# CSSKeywordValue

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSKeywordValue` interface of the [CSS Typed Object Model API](css_object_model#css_typed_object_model) creates an object to represent CSS keywords and other identifiers. The interface instance name is a stringifier meaning that when used anywhere a string is expected it will return the value of `CSSKeyword.value`.

## Constructor

[`CSSKeywordValue.CSSKeywordValue()`](csskeywordvalue/csskeywordvalue)  
Creates a new `CSSKeywordValue` object.

## Properties

[`CSSKeywordValue.value`](csskeywordvalue/value)  
Returns or sets the value of the `CSSKeywordValue`.

## Methods

_Inherits methods from [`CSSStyleValue`](cssstylevalue)._

## Examples

The following example resets the CSS [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property to its defaults, setting the inline `style` attribute to `style="display: initial"` if viewed in the [developer tools inspector](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Select_an_element).

    let myElement = document.getElementById('myElement').attributeStyleMap;
        myElement.set('display', new CSSKeywordValue('initial'));

    console.log( myElement.get('display').value);  // 'initial'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#keywordvalue-objects">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSKeywordValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSKeywordValue`

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

`CSSKeywordValue`

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

`value`

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
- [`CSSNumericValue`](cssnumericvalue)
- [`CSSPositionValue`](csspositionvalue)
- [`CSSTransformValue`](csstransformvalue)
- [`CSSUnparsedValue`](cssunparsedvalue)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSKeywordValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSKeywordValue</a>
