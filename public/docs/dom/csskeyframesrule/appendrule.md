# CSSKeyframesRule.appendRule()

The `appendRule()` method of the [`CSSKeyframeRule`](../csskeyframerule) interface appends a [`CSSKeyFrameRule`](../csskeyframerule) to the end of the rules.

## Syntax

    CSSKeyframesRule.appendRule(rule);

### Parameters

`rule`  
A [`CSSOMString`](../cssomstring) containing a keyframe rule.

### Return value

None.

## Example

The CSS includes a keyframes at-rule. This will be the first [`CSSRule`](../cssrule) returned by `document.styleSheets[0].cssRules`. `myRules[0]` returns a [`CSSKeyframesRule`](../csskeyframesrule) object. Returning the `cssRules` property would return a [`CSSRuleList`](../cssrulelist) containing one rule.

After appending another rule with `appendRule` the `cssRules` property returns a [`CSSRuleList`](../cssrulelist) containing two rules.

    @keyframes slidein {
      from {
        transform: translateX(0%);
      }
    }

    let myRules = document.styleSheets[0].cssRules;
    let keyframes = myRules[0]; // a CSSKeyframesRule
    keyframes.appendRule('to {transform: translateX(100%);}');
    console.log(keyframes.cssRules); // a CSSRuleList object with two rules

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#interface-csskeyframesrule-appendrule">CSS Animations Level 1<br />
<span class="small">The definition of 'CSSKeyframesRule.appendRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`appendRule`

41

1-45

12

22

5-22

10

28

15-31

12-15

9.1

4

41

1-45

41

18-45

22

5-22

28

14-32

12-14

9.3

3.2

4.0

1.0-5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule/appendRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule/appendRule</a>
