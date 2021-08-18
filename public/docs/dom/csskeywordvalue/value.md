# CSSKeywordValue.value

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `value` property of the [`CSSKeywordValue`](../csskeywordvalue) interface returns or sets the value of the `CSSKeywordValue`.

## Syntax

    var val = cssKeywordValue.value
    cssKeywordValue.value = val

### Value

A [`USVString`](../usvstring).

### Exceptions

`TypeError`  
If the `value` property is an empty [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) when being set.

## Examples

The following example resets the CSS [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property to its defaults.

    let indicator = document.getElementById('indicator');
    indicator.attributeStyleMap.set('display', new CSSKeywordValue('initial'));
    indicator.attributeStyleMap.get('display').value // 'initial'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-csskeywordvalue-value">CSS Typed OM Level 1<br />
<span class="small">The definition of 'undefined' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSKeywordValue/value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSKeywordValue/value</a>
