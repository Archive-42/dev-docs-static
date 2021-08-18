# CSSKeyframesRule

The `CSSKeyframesRule` interface describes an object representing a complete set of keyframes for a CSS animation. It corresponds to the contents of a whole [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes) [`at-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule).

## Properties

_Inherits properties from its ancestor [`CSSRule`](cssrule)._

[`CSSKeyframesRule.name`](csskeyframesrule/name)  
Represents the name of the keyframes, used by the [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name) property.

[`CSSKeyframesRule.cssRules`](csskeyframesrule/cssrules) <span class="badge inline readonly">Read only </span>  
Returns a [`CSSRuleList`](cssrulelist) of the keyframes in the list.

## Methods

_Inherits methods from its ancestor [`CSSRule`](cssrule)._

[`CSSKeyframesRule.appendRule()`](csskeyframesrule/appendrule)  
Inserts a new keyframe rule into the current CSSKeyframesRule. The parameter is a [`DOMString`](domstring) containing a keyframe in the same format as an entry of a [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes) at-rule. If it contains more than one keyframe rule, a [`DOMException`](domexception) with a `SYNTAX_ERR` is thrown.

[`CSSKeyframesRule.deleteRule()`](csskeyframesrule/deleterule)  
Deletes a keyframe rule from the current CSSKeyframesRule. The parameter is the index of the keyframe to be deleted, expressed as a [`DOMString`](domstring) resolving as a number between `0%` and `100%`.

[`CSSKeyframesRule.findRule()`](csskeyframesrule/findrule)  
Returns a keyframe rule corresponding to the given key. The key is a [`DOMString`](domstring) containing an index of the keyframe to be returned, resolving to a percentage between `0%` and `100%`. If no such keyframe exists, `findRule` returns `null`.

## Example

The CSS includes a keyframes at-rule. This will be the first [`CSSRule`](cssrule) returned by `document.styleSheets[0].cssRules`. `myRules[0]` returns a [`CSSKeyframesRule`](csskeyframesrule) object.

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#interface-csskeyframesrule">CSS Animations Level 1<br />
<span class="small">The definition of 'CSSKeyframesRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`CSSKeyframesRule`

31

1-31

12

48

5-48

10

18

15-18

12.1-15

12-12.1

9.1

4-9.1

4.4.3

1-4.4.3

31

18-31

48

5-48

18

14-18

12.1-14

12-12.1

9.3

3.2-9.3

2.0

1.0-2.0

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

`name`

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

## See also

- [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
- [`CSSKeyFrameRule`](csskeyframerule)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule</a>
