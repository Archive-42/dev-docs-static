# CSSSupportsRule

The `CSSSupportsRule` interface represents a single CSS [`@supports`](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports) [`at-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule).

## Properties

_Inherits properties from its ancestors [`CSSConditionRule`](cssconditionrule), [`CSSGroupingRule`](cssgroupingrule), and [`CSSRule`](cssrule)._

## Methods

_Inherits methods from its ancestors [`CSSConditionRule`](cssconditionrule), [`CSSGroupingRule`](cssgroupingrule), and [`CSSRule`](cssrule)._

## Examples

The CSS includes a CSS feature query using the [`@supports`](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports) [`at-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule), containing one style rule. This will be the first CSSRule returned by `document.styleSheets[0].cssRules`. `myRules[0]` therefore returns a [`CSSSupportsRule`](csssupportsrule) object.

    @supports (display: grid) {
      body {
        color: blue;
      }
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0]); // a CSSSupportsRule representing the feature query.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-conditional-3/#the-csssupportsrule-interface">CSS Conditional Rules Module Level 3<br />
<span class="small">The definition of 'CSSSupportsRule' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`CSSSupportsRule`

28

12

22

No

12.1

9

≤37

28

22

15

12.1-14

9

1.5

## See also

- [`@supports`](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSSupportsRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSSupportsRule</a>
