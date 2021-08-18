# CSSKeywordValue.CSSKeywordValue()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSKeywordValue` constructor creates a new [`CSSKeywordValue`](../csskeywordvalue) object which represents CSS keywords and other identifiers.

## Syntax

    var cssKeywordValue = new CSSKeywordValue(val)

### Parameters

value  
Sets or returns the value of the new `CSSKeywordValue`.

### Exceptions

`TypeError`  
If the `value` parameter is not specified or it is not of type [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

## Examples

The following example resets the CSS [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property to its defaults, setting the inline `style` attribute to `style="display: initial"` if viewed in the [developer tools inspector](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Select_an_element).

    let keyword = new CSSKeywordValue('initial');
    let myElement = document.getElementById('myElement').attributeStyleMap;
        myElement.set('display', keyword);

    console.log( myElement.get('display').value);  // 'initial'
    console.dir( keyword );

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-csskeywordvalue-csskeywordvalue">CSS Typed OM Level 1<br />
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSKeywordValue/CSSKeywordValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSKeywordValue/CSSKeywordValue</a>
