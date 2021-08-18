# CSSStyleValue.parseAll()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `parseAll()` method of the [`CSSStyleValue`](../cssstylevalue) interface sets all occurrences of a specific CSS property to the specified value and returns an array of [`CSSStyleValue`](../cssstylevalue) objects, each containing one of the supplied values.

## Syntax

    CSSStyleValue.parseAll(property, value)

### Parameters

property  
A CSS property to set.

cssText  
A comma-separated string containing one or more values that apply to the provided property.

### Return value

An array of `CSSStyleValue` objects, each containing one of the supplied values.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssstylevalue-parseall">CSS Typed OM Level 1<br />
<span class="small">The definition of 'parseAll()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [`CSSStyleValue.parse()`](parse)
- [Using the CSS Typed OM](../css_typed_om_api/guide)
- [CSS Typed Object Model API](../css_typed_om_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleValue/parseAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleValue/parseAll</a>
