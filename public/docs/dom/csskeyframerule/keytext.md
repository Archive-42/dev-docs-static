# CSSKeyframeRule.keyText

The `keyText` property of the [`CSSKeyframeRule`](../csskeyframerule) interface represents the keyframe selector as a comma-separated list of percentage values. The from and to keywords map to 0% and 100%, respectively.

## Syntax

    var text = CSSKeyframeRule.keyText;
    CSSKeyframeRule.keyText = text;

### Value

A [`CSSOMString`](../cssomstring).

### Exceptions

[`SyntaxError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError)  
Thrown if `keyText` is updated with an invalid keyframe selector, in which case `keyText` remains untouched.

## Example

The CSS includes a keyframes at-rule. This will be the first [`CSSRule`](../cssrule) returned by `document.styleSheets[0].cssRules`. `myRules[0]` returns a [`CSSKeyframesRule`](../csskeyframesrule) object, which will contain individual <span class="page-not-created">`CSSKeyFrame`</span> objects for each keyframe.

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
    console.log(keyframes[0].keyText); // a string containing 0%

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#dom-csskeyframerule-keytext">CSS Animations Level 1<br />
<span class="small">The definition of 'CSSKeyframeRule.keyText' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`keyText`

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

4

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframeRule/keyText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframeRule/keyText</a>
