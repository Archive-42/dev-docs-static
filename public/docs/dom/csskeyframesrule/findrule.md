# CSSKeyframesRule.findRule()

The `findRule()` method of the [`CSSKeyframeRule`](../csskeyframerule) interface finds the [`CSSKeyFrameRule`](../csskeyframerule) that matches the specified keyframe selector.

## Syntax

    CSSKeyframesRule.findRule(select);

### Parameters

`select`  
A [`CSSOMString`](../cssomstring) which contains the keyframe selector of the rule to be found, which must be:

- a comma-separated list of percentage values between 0% and 100%;
- or, the keywords `from` or `to`

Note that the number and order of the values in the specified keyframe selector must match those of the targeted keyframe rule(s). White-space is disregarded.

### Return value

A [`CSSKeyframeRule`](../csskeyframerule) which is the last matching rule. If no rules are found, nothing is returned.

## Example

The CSS includes a keyframes at-rule. This will be the first [`CSSRule`](../cssrule) returned by `document.styleSheets[0].cssRules`. `myRules[0]` returns a [`CSSKeyframesRule`](../csskeyframesrule) object. Calling findRule("to") returns a [`CSSKeyframeRule`](../csskeyframerule) representing the second rule.

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
    console.log(keyframes.findRule('to'));  // a CSSKeyframeRule object

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#interface-csskeyframesrule-findrule">CSS Animations Level 1<br />
<span class="small">The definition of 'CSSKeyframesRule.findRule()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`findRule`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule/findRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule/findRule</a>
