# CSSPageRule

`CSSPageRule` represents a single CSS [`@page`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page) rule.

## Properties

_Inherits properties from its ancestor [`CSSRule`](cssrule)._

[`CSSPageRule.selectorText`](csspagerule/selectortext)  
Represents the text of the page selector associated with the at-rule.

[`CSSPageRule.style`](csspagerule/style) <span class="badge inline readonly">Read only </span>  
Returns the [declaration block](css_object_model/css_declaration_block) associated with the at-rule.

## Methods

_Inherits methods from its ancestor [`CSSRule`](cssrule)._

## Examples

The stylesheet includes a single [`@page`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page) rule, therefore the first (and only) rule returned will be a `CSSPageRule`.

    @page {
      margin: 1cm;
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0]); // a CSSPageRule

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#the-csspagerule-interface">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSPageRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No changes from <a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSPageRule">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSPageRule' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`CSSPageRule`

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

`selectorText`

1

12

No

9

≤12.1

3

1

18

No

≤12.1

1

1.0

`style`

1

12

12

9

≤12.1

3

1

18

14

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPageRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPageRule</a>
