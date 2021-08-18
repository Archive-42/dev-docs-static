# CSSKeyframesRule.deleteRule()

The `deleteRule()` method of the [`CSSKeyframeRule`](../csskeyframerule) interface deletes the [`CSSKeyFrameRule`](../csskeyframerule) that matches the specified keyframe selector.

## Syntax

    CSSKeyframesRule.deleteRule(select);

### Parameters

`select`  
A [`CSSOMString`](../cssomstring) which contains the keyframe selector of the rule to be deleted, which must be:

- a comma-separated list of percentage values between 0% and 100%;
- or, the keywords `from` or `to`

Note that the number and order of the values in the specified keyframe selector must match those of the targeted keyframe rule(s). White-space is disregarded.

### Return value

None.

## Example

The CSS includes a keyframes at-rule. This will be the first [`CSSRule`](../cssrule) returned by `document.styleSheets[0].cssRules`. `myRules[0]` returns a [`CSSKeyframesRule`](../csskeyframesrule) object. Returning the `cssRules` property would return a [`CSSRuleList`](../cssrulelist) containing two rules.

After deleting a rule with `deleteRule()` the `cssRules` property returns a [`CSSRuleList`](../cssrulelist) containing one rule.

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
    keyframes.deleteRule('to');
    console.log(keyframes.cssRules); // a CSSRuleList object with one rule

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#dom-csskeyframesrule-deleterule">CSS Animations Level 1<br />
<span class="small">The definition of 'CSSKeyframesRule.deleteRule()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`deleteRule`

1

12

5

10

12

4

1

18

5

12

3.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule/deleteRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule/deleteRule</a>
