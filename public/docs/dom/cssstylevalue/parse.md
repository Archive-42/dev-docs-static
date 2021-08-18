# CSSStyleValue.parse()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `parse()` method of the [`CSSStyleValue`](../cssstylevalue) interface sets a specific CSS property to the specified values and returns the first value as a [`CSSStyleValue`](../cssstylevalue) object.

## Syntax

    CSSStyleValue.parse(property, cssText)

### Parameters

property  
A CSS property to set.

cssText  
A comma-separated string containing one or more values to apply to the provided property.

### Return value

A `CSSStyleValue` object containing the first supplied value.

## Example

The code below parses a set of declarations for the `transform` property. The second code block shows the structure of the returned object as it would be rendered in a developer tools console.

    const css = CSSStyleValue.parse(
        'transform', 'translate3d(10px,10px,0) scale(0.5)');

    CSSTransformValue {0: CSSTranslate, 1: CSSScale, length: 2, is2D: false}

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssstylevalue-parse">CSS Typed OM Level 1<br />
<span class="small">The definition of 'parse()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [`CSSStyleValue.parseAll()`](parseall)
- [Using the CSS Typed OM](../css_typed_om_api/guide)
- [CSS Typed Object Model API](../css_typed_om_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleValue/parse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleValue/parse</a>
