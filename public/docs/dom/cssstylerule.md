# CSSStyleRule

The `CSSStyleRule` interface represents a single CSS style rule.

## Properties

_Inherits properties from its ancestor [`CSSRule`](cssrule)._

[`CSSStyleRule.selectorText`](cssstylerule/selectortext)  
Returns the textual representation of the selector for this rule, e.g. `"h1,h2"`.

[`CSSStyleRule.style`](cssstylerule/style) <span class="badge inline readonly">Read only </span>  
Returns the [`CSSStyleDeclaration`](cssstyledeclaration) object for the rule.

[`CSSStyleRule.styleMap`](cssstylerule/stylemap) <span class="badge inline readonly">Read only </span>  
Returns a [`StylePropertyMap`](stylepropertymap) object which provides access to the rule's property-value pairs.

## Methods

_No specific methods; inherits methods from its ancestor [`CSSRule`](cssrule)._

## Examples

The CSS includes one style rule. This will be the first [`CSSRule`](cssrule) returned by `document.styleSheets[0].cssRules`. `myRules[0]` therefore returns a [`CSSStyleRule`](cssstylerule) object representing the rule defined for `h1`.

    h1 {
      color: pink;
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0]); // a CSSStyleRule representing the h1.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#the-cssstylerule-interface">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No changes</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSStyleRule">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSRule' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

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

`CSSStyleRule`

1

12

1

9

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`selectorText`

1

12

1

9

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`style`

1

12

1

9

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`styleMap`

66

79

No

No

53

No

66

66

No

47

No

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule</a>
