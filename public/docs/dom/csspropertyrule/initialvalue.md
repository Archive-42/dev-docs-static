# CSSPropertyRule.initialValue

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `initialValue` nullable property of the [`CSSPropertyRule`](../csspropertyrule) interface returns the initial value of the custom property registration represented by the [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) rule, controlling the property’s initial value.

## Syntax

    const initialValue = CSSPropertyRule.initialValue;

### Value

A [`USVString`](../usvstring) which is a <span class="page-not-created">`<declaration-value>`</span> as defined in [CSS Syntax 3](https://www.w3.org/TR/css-syntax-3/#typedef-declaration-value).

## Examples

This stylesheet contains a single [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) rule. The first [`CSSRule`](../cssrule) returned will be a `CSSPropertyRule` representing this rule. The `initialValue` property returns the string `"#c0ffee"` this being the value of the `initial-value` property in the CSS.

    @property --property-name {
      syntax: '<color>';
      inherits: false;
      initial-value: #c0ffee;
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].initialValue); //the string "#c0ffee"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-properties-values-api-1/#dom-csspropertyrule-initialvalue">CSS Properties and Values API Level 1<br />
<span class="small">The definition of 'InitialValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`initialvalue`

85

85

No

No

71

No

85

85

No

60

No

14.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPropertyRule/initialvalue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPropertyRule/initialvalue</a>
