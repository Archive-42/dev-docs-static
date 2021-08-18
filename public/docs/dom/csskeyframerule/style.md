# CSSKeyframeRule.style

The read-only `CSSKeyframeRule.style` property is the [`CSSStyleDeclaration`](../cssstyledeclaration) interface for the [declaration block](https://www.w3.org/TR/1998/REC-CSS2-19980512/syndata.html#block) of the [`CSSKeyframeRule`](../csskeyframerule).

## Syntax

    styleObj = cssKeyframeRule.style

### Value

A [`CSSStyleDeclaration`](../cssstyledeclaration) object, with the following properties:

computed flag  
Unset.

declarations  
The declared declarations in the rule, in the order they were specified, shorthand properties expanded to longhands.

parent CSS rule  
The context object, which is an alias for [this](https://heycam.github.io/webidl/#this).

owner node  
Null.

## Example

The CSS includes a [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes) at-rule. This will be the first [`CSSRule`](../cssrule) returned by `document.styleSheets[0].cssRules`. `myRules[0]` returns a [`CSSKeyframesRule`](../csskeyframesrule) object, which will contain individual `CSSKeyFrame` objects for each keyframe.

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
    console.log(keyframes[0].style); // a CSSStyleDeclaration

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#dom-csskeyframerule-style">CSS Animations Level 1<br />
<span class="small">The definition of 'CSSKeyframeRule.style' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`style`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSkeyframeRule/style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSkeyframeRule/style</a>
