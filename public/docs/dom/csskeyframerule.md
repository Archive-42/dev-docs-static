# CSSKeyframeRule

The `CSSKeyframeRule` interface describes an object representing a set of styles for a given keyframe. It corresponds to the contents of a single keyframe of a [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes) [`at-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule).

## Properties

_Inherits properties from its ancestor [`CSSRule`](cssrule)._

[`CSSKeyframeRule.keyText`](csskeyframerule/keytext)  
Represents the key of the keyframe, like `'10%'`, `'75%'`. The `from` keyword maps to `'0%'` and the `to` keyword maps to `'100%'`.

[`CSSKeyframeRule.style`](csskeyframerule/style)<span class="badge inline readonly">Read only </span>  
Returns a [`CSSStyleDeclaration`](cssstyledeclaration) of the CSS style associated with the keyframe.

## Methods

_No specific methods; inherits methods from its ancestor [`CSSRule`](cssrule)._

## Examples

The CSS includes a keyframes at-rule. This will be the first [`CSSRule`](cssrule) returned by `document.styleSheets[0].cssRules`. `myRules[0]` returns a [`CSSKeyframesRule`](csskeyframesrule) object, which will contain individual `CSSKeyFrame` objects for each keyframe.

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
    console.log(keyframes[0]); // a CSSKeyframeRule representing an individual keyframe.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#interface-csskeyframerule">CSS Animations Level 1<br />
<span class="small">The definition of 'CSSKeyframeRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`CSSKeyframeRule`

31

1-31

12

48

5-48

10

18

15-18

12-15

9

4-9

4.4.3

1-4.4.3

31

18-31

48

5-48

18

14-18

12-14

9

3.2-9

2.0

1.0-2.0

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

## See also

- [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
- [`CSSKeyFramesRule`](csskeyframesrule)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframeRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframeRule</a>
