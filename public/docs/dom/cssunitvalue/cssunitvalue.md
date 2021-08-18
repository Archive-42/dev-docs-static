# CSSUnitValue.CSSUnitValue()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSUnitValue()` constructor creates a new [`CSSUnitValue`](../cssunitvalue) object which returns a new [`CSSUnitValue`](../cssunitvalue) object which represents values that contain a single unit type. For example, "42px" would be represented by a `CSSNumericValue`.

## Syntax

    var CSSUnitValue = new CSSUnitValue()

### Parameters

value  
Returns a double indicating the number of units.

unit  
Returns a <span class="page-not-created">`USVString`</span> indicating the type of unit.

## Examples

The following shows a method of creating a [`CSSPositionValue`](../csspositionvalue) from individual `CSSUnitValue` constructors.

    let pos = new CSSPositionValue(
        new CSSUnitValue(5, "px"),
        new CSSUnitValue(10, "px"));

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#simple-numeric">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSUnitValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSUnitValue`

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

- [`CSSUnitValue.unit`](unit)
- [`CSSUnitValue.value`](value)
- [Using the CSS Typed OM](../css_typed_om_api/guide)
- [CSS Typed Object Model API](../css_typed_om_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSUnitValue/CSSUnitValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSUnitValue/CSSUnitValue</a>
