# CSSUnparsedValue.entries()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSUnparsedValue.entries()` method returns an array of a given object's own enumerable property `[key, value]` pairs in the same order as that provided by a [`for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in) loop (the difference being that a for-in loop enumerates properties in the prototype chain as well).

## Syntax

    CSSUnparsedValue.entries(obj)

### Parameters

`obj`  
The [`CSSUnparsedValue`](../cssunparsedvalue) whose enumerable own property `[key, value]` pairs are to be returned.

### Return value

An array of the given `CSSUnparsedValue` object's own enumerable property `[key, value]` pairs.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#cssunparsedvalue">CSS Typed OM Level 1<br />
<span class="small">The definition of 'entries()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [`CSSUnparsedValue.CSSUnparsedValue()`](cssunparsedvalue)
- [`CSSUnparsedValue.forEach`](foreach)
- [`CSSUnparsedValue.keys`](keys)
- [`CSSUnparsedValue.length`](length)
- [`CSSUnparsedValue.values`](values)
- [Using the CSS Typed OM](../css_typed_om_api/guide)
- [CSS Typed Object Model API](../css_typed_om_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSUnparsedValue/entries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSUnparsedValue/entries</a>
