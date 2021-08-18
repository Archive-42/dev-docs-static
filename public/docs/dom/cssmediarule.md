# CSSMediaRule

The `CSSMediaRule` interface represents a single CSS [`@media`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media) rule.

## Properties

_Inherits properties from its ancestors [`CSSConditionRule`](cssconditionrule), [`CSSGroupingRule`](cssgroupingrule), and [`CSSRule`](cssrule)._

[`CSSMediaRule.media`](cssmediarule/media) <span class="badge inline readonly">Read only </span>  
Returns a [`MediaList`](medialist) representing the intended destination medium for style information.

## Methods

_No specific methods; inherits methods from its ancestors [`CSSConditionRule`](cssconditionrule), [`CSSGroupingRule`](cssgroupingrule), and [`CSSRule`](cssrule)._

## Examples

The CSS includes a media query with one style rule. This will be the first CSSRule returned by `document.styleSheets[0].cssRules`. `myRules[0]` therefore returns a [`CSSMediaRule`](cssmediarule) object.

    @media (min-width: 500px) {
      body {
        color: blue;
      }
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0]); // a CSSMediaRule representing the media query.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-conditional-3/#the-cssmediarule-interface">CSS Conditional Rules Module Level 3<br />
<span class="small">The definition of 'CSSMediaRule' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Make it derived from the <a href="cssconditionrule"><code>CSSConditionRule</code></a>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/cssom/#the-cssmediarule-interface">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSMediaRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No changes from <a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSMediaRule">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSMediaRule' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

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

`CSSMediaRule`

1

12

1

Before Firefox 20, `conditionText` could not be set.

9

≤12.1

3

1

18

4

Before Firefox 20, `conditionText` could not be set.

≤12.1

1

1.0

`media`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule</a>
