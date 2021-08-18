# CSSKeyframesRule.cssRules

The read-only `cssRules` property of the [`CSSKeyframeRule`](../csskeyframerule) interface returns a [`CSSRuleList`](../cssrulelist) containing the rules in the keyframes [`at-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule).

## Syntax

    var cssRules = CSSKeyframesRule.cssRules;

### Value

A [`CSSRuleList`](../cssrulelist).

## Example

The CSS includes a keyframes at-rule. This will be the first [`CSSRule`](../cssrule) returned by `document.styleSheets[0].cssRules`. `myRules[0]` returns a [`CSSKeyframesRule`](../csskeyframesrule) object. The `cssRules` property returns a [`CSSRuleList`](../cssrulelist) containing two rules.

    @keyframes slidein {
      from {
        transform: translateX(0%);
      }

      to {
        transform: translateX(100%);
      }
    }

    let myRules = document.styleSheets[0].cssRules;
    let keyframes = myRules[0]; // a CSSKeyframesRule
    console.log(keyframes.cssRules); // a CSSRuleList object with two rules

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#dom-csskeyframesrule-cssrules">CSS Animations Level 1<br />
<span class="small">The definition of 'CSSKeyframesRule.cssRules' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

44

12

5

10

31

9.1

44

44

5

32

9.3

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule/cssRules" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule/cssRules</a>
