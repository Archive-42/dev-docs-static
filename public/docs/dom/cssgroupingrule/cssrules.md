# CSSGroupingRule.cssRules

The `cssRules` property of the [`CSSGroupingRule`](../cssgroupingrule) interface returns a [`CSSRuleList`](../cssrulelist) containing a collection of [`CSSRule`](../cssrule) objects.

## Syntax

    var cssRules = cssGroupingRule.cssRules;

### Value

a [`CSSRuleList`](../cssrulelist).

## Examples

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssgroupingrule-cssrules">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSRules' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`cssRules`

45

12

20

No

32

No

45

45

20

32

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule/cssRules" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule/cssRules</a>
