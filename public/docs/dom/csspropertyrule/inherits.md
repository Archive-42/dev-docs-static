# CSSPropertyRule.inherits

The read-only `inherits` property of the [`CSSPropertyRule`](../csspropertyrule) interface returns the inherit flag of the custom property registration represented by the [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) rule, a boolean describing whether or not the property inherits by default.

## Syntax

    const inherits = CSSPropertyRule.inherits;

### Value

A boolean.

## Examples

This stylesheet contains a single [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) rule. The first [`CSSRule`](../cssrule) returned will be a `CSSPropertyRule` representing this rule. The `inherits` property returns the boolean `false`, this being the value of the `inherits` property in the CSS.

    @property --property-name {
      syntax: '<color>';
      inherits: false;
      initial-value: #c0ffee;
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].inherits); //returns false

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-properties-values-api-1/#dom-csspropertyrule-inherits">CSS Properties and Values API Level 1<br />
<span class="small">The definition of 'Inherits' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`inherits`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPropertyRule/inherits" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPropertyRule/inherits</a>
