# CSSPropertyRule.name

The read-only `name` property of the [`CSSPropertyRule`](../csspropertyrule) interface represents the property name, this being the serialization of the name given to the custom property in the [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) rule’s prelude.

## Syntax

    const name = CSSPropertyRule.name;

### Value

A [`USVString`](../usvstring).

## Examples

This stylesheet contains a single [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) rule. The first [`CSSRule`](../cssrule) returned will be a `CSSPropertyRule` representing this rule. The `name` property returns the string `"--property-name"`, which is the name given to the custom property in CSS.

    @property --property-name {
      syntax: '<color>';
      inherits: false;
      initial-value: #c0ffee;
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].name); //the string "--property-name"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-properties-values-api-1/#dom-csspropertyrule-name">CSS Properties and Values API Level 1<br />
<span class="small">The definition of 'Name' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`name`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPropertyRule/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPropertyRule/name</a>
