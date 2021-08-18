# CSSPropertyRule.syntax

The read-only `syntax` property of the [`CSSPropertyRule`](../csspropertyrule) interface returns the literal syntax of the custom property registration represented by the [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) rule, controlling how the property’s value is parsed at computed-value time.

## Syntax

    const syntax = CSSPropertyRule.syntax;

### Value

A [`USVString`](../usvstring).

## Examples

This stylesheet contains a single [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) rule. The first [`CSSRule`](../cssrule) returned will be a `CSSPropertyRule` representing this rule. The `syntax` property returns the literal string `"<color>"`.

    @property --property-name {
      syntax: '<color>';
      inherits: false;
      initial-value: #c0ffee;
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].syntax); //the string "<color>"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-properties-values-api-1/#dom-csspropertyrule-syntax">CSS Properties and Values API Level 1<br />
<span class="small">The definition of 'Syntax' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`syntax`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPropertyRule/syntax" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPropertyRule/syntax</a>
