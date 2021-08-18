# CSSRuleList

A `CSSRuleList` is an (indirect-modify only) array-like object containing an ordered collection of `CSSRule` objects.

## Description

Each `CSSRule` can be accessed as `rules.item(index),` or `rules[index]`, where `rules` is an object implementing the `CSSRuleList` interface (such as `CSSStylesheet.cssRules`), and `index` is the 0-based index of the rule, in the order as it appears in the style sheet CSS. The number of rules in the list is `rules.length`.

Note that being _indirect-modify_ ([changeable](https://www.w3.org/TR/cssom/#cssstylesheet) but [only having](https://www.w3.org/TR/cssom/#cssrulelist) read-methods), rules are **NOT** added or removed from the list directly, but instead here, only via its parent stylesheet. In fact, [`.insertRule()`](cssstylesheet/insertrule) and [`.deleteRule()`](cssstylesheet/deleterule) are not even methods of CSSRuleList, but only of [`CSSStyleSheet`](cssstylesheet). If however, for some reason the list does need to be modified but has no parent stylesheet (perhaps being a _[livecopy](https://www.w3.org/TR/cssom/#cssstylesheet)_ of a list that does), it cannot just be assigned one (as it has [no such property](https://www.w3.org/TR/cssom/#cssrulelist)), and neither can it be assigned to one (as stylesheet.css`Rules `is [read-only](https://www.w3.org/TR/cssom/#cssstylesheet)), but it must unfortunately be **inserted** into one, rule by rule, and unless combining lists, after any existing list therein is deleted, rule by rule.

## Examples

### Simple usage

    // get the first style sheet’s first rule
    var first_rule = document.styleSheets[0].cssRules[0];

### CSSRuleList implementations

There are multiple properties in the CSSOM that will return a `CSSRuleList`. They are:

- [`CSSStyleSheet`](cssstylesheet) property [`cssRules`](cssstylesheet/cssrules)
- [`CSSMediaRule`](cssmediarule) property <span class="page-not-created">`cssRules`</span>
- [`CSSKeyframesRule`](csskeyframesrule) property [`cssRules`](csskeyframesrule/cssrules)
- <span class="page-not-created">`CSSMozDocumentRule`</span> property <span class="page-not-created">`cssRules`</span>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#the-cssrulelist-interface">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSRuleList' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`CSSRuleList`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`item`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`length`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- `CSSRule`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSRuleList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSRuleList</a>
