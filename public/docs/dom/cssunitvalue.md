# CSSUnitValue

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSUnitValue` interface of the [CSS_Object_Model\#css_typed_object_model](css_object_model#css_typed_object_model) represents values that contain a single unit type. For example, "42px" would be represented by a `CSSNumericValue`.

## Constructor

[`CSSStyleValue.CSSUnitValue()`](cssunitvalue/cssunitvalue)  
Creates a new `CSSUnitValue` object.

## Properties

[`CSSUnitValue.value`](cssunitvalue/value)  
Returns a double indicating the number of units.

[`CSSUnitValue.unit`](cssunitvalue/unit)  
Returns a <span class="page-not-created">`USVString`</span> indicating the type of unit.

### Event handlers

None.

## Methods

None.

## Examples

The following shows a method of creating a [`CSSPositionValue`](csspositionvalue) from individual `CSSUnitValue` constructors.

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

`unit`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSUnitValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSUnitValue</a>
