# CSSUnitValue.value

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSUnitValue.value` property of the [`CSSUnitValue`](../cssunitvalue) interface returns a double indicating the number of units.

## Syntax

    var cssUnitValue = CSSUnitValue.value;
    CSSUnitValue.value = cssUnitValue;

### Value

A double.

## Examples

The following creates a [`CSSPositionValue`](../csspositionvalue) from individual `CSSUnitValue` constructors, then queries the `CSSUnitValue.value`.

    let pos = new CSSPositionValue(
        new CSSUnitValue( 5, "px" ),
        new CSSUnitValue( 10, "px" ));

    console.log( pos.x.value ); // 5
    console.log( pos.y.value ); // 10

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssunitvalue-value">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSUnitValue.value' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

- [`CSSUnitValue.unit`](unit)
- [Using the CSS Typed OM](../css_typed_om_api/guide)
- [CSS Typed Object Model API](../css_typed_om_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSUnitValue/value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSUnitValue/value</a>
