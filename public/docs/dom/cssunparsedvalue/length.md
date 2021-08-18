# CSSUnparsedValue.length

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `length` read-only property of the [`CSSUnparsedValue`](../cssunparsedvalue) interface returns the number of items in the object.

## Syntax

    var length = CSSUnparsedValue.length;

### Value

An integer.

## Examples

In this example we employ the [`CSSUnparsedValue.CSSUnparsedValue()`](cssunparsedvalue) constructor, then query the length:

    let values = new CSSUnparsedValue( ['1em', '#445566', '-45px'] );

    console.log( values.length ) // 3

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssunparsedvalue-length">CSS Typed OM Level 1<br />
<span class="small">The definition of 'length' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [`CSSUnparsedValue.CSSUnparsedValue()`](cssunparsedvalue)
- [`CSSUnparsedValue.entries`](entries)
- [`CSSUnparsedValue.forEach`](foreach)
- [`CSSUnparsedValue.keys`](keys)
- [`CSSUnparsedValue.values`](values)
- [Using the CSS Typed OM](../css_typed_om_api/guide)
- [CSS Typed Object Model API](../css_typed_om_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSUnparsedValue/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSUnparsedValue/length</a>
