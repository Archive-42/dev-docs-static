# CSSUnparsedValue.forEach()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSUnparsedValue.forEach()` method executes a provided function once for each element of the [`CSSUnparsedValue`](../cssunparsedvalue).

## Syntax

    CSSUnparsedValue.forEach(function callback(currentValue[, index[, array]]) {
        // your iterator
    }[, thisArg]);

### Parameters

`callback`  
The function to execute for each element, taking three arguments:

`currentValue`  
The value of the current element being processed.

`index`<span class="badge inline optional">Optional</span>  
The index of the current element being processed.

`array`<span class="badge inline optional">Optional</span>  
The `CSSUnparsedValue` that `forEach()` is being called on.

`thisArg` <span class="badge inline optional">Optional</span>  
Value to use as `this` (i.e the reference `Object`) when executing `callback`.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#cssunparsedvalue">CSS Typed OM Level 1<br />
<span class="small">The definition of 'forEach()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [`CSSUnparsedValue.CSSUnparsedValue()`](cssunparsedvalue)
- [`CSSUnparsedValue.entries`](entries)
- [`CSSUnparsedValue.keys`](keys)
- [`CSSUnparsedValue.length`](length)
- [`CSSUnparsedValue.values`](values)
- [Using the CSS Typed OM](../css_typed_om_api/guide)
- [CSS Typed Object Model API](../css_typed_om_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSUnparsedValue/forEach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSUnparsedValue/forEach</a>
