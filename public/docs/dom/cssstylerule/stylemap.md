# CSSStyleRule.styleMap

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `styleMap` read-only property of the [`CSSStyleRule`](../cssstylerule) interface returns a [`StylePropertyMap`](../stylepropertymap) object which provides access to the rule's property-value pairs.

## Syntax

    var stylePropertyMap = cssStyleRule.styleMap;

### Value

A [`StylePropertyMap`](../stylepropertymap) object.

## Example

The following example shows `styleMap` being used to modify a style using the [`StylePropertyMap.set()`](../stylepropertymap/set) method.

    const stylesheet = document.styleSheets[0];

    Object.values(stylesheet.cssRules).forEach(block => {
      if (block.selectorText === 'button') {
        block.styleMap.set('--mainColour', 'black');
      }
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssstylerule-stylemap">CSS Typed OM Level 1<br />
<span class="small">The definition of 'styleMap' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`styleMap`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule/styleMap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule/styleMap</a>
