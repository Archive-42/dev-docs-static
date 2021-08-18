# CSSStyleSheet.cssRules

The read-only [`CSSStyleSheet`](../cssstylesheet) property `cssRules` returns a live [`CSSRuleList`](../cssrulelist) which provides a real-time, up-to-date list of every CSS rule which comprises the stylesheet. Each item in the list is a [`CSSRule`](../cssrule) defining a single rule.

## Syntax

    var rules = cssStyleSheet.cssRules;

### Value

A live-updating [`CSSRuleList`](../cssrulelist) containing each of the CSS rules making up the stylesheet. Each entry in the rule list is a [`CSSRule`](../cssrule) object describing one rule making up the stylesheet.

## Examples

Individual rules within the stylesheet can then be accessed by index:

    let ruleList = document.styleSheets[0].cssRules;

    for (let i=0; i < ruleList.length; i++) {
      processRule(ruleList[i]);
    }

Rules can also be accessed using <span class="page-not-created">`for...of`</span>:

    let ruleList = document.styleSheets[0].cssRules;

    for (let rule of ruleList) {
      processRule(rule);
    }

However, because `CSSRule` is not a proper array, you can't use [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstylesheet-cssrules">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleSheet.cssRules' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`cssRules`

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

- [CSS Object Model](../css_object_model)
- [Using dynamic styling information](../css_object_model/using_dynamic_styling_information)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/cssRules" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/cssRules</a>
