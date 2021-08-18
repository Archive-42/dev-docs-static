# CSSStyleSheet.ownerRule

The read-only [`CSSStyleSheet`](../cssstylesheet) property `ownerRule` returns the [`CSSImportRule`](../cssimportrule) corresponding to the [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) at-rule which imported the stylesheet into the document. If the stylesheet wasn't imported into the document using `@import`, the returned value is `null`.

## Syntax

    var ownerRule = cssStyleSheet.ownerRule;

### Value

A [`CSSImportRule`](../cssimportrule) corresponding to the [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) rule which imported the stylesheet into the document. If the stylesheet wasn't imported into the document using `@import`, the returned value is `null`.

## Examples

This snippet of code looks for rules which were not imported into the document using an `@import` at-rule.

    let ruleList = document.styleSheets[0].cssRules;

    for (let rule of ruleList) {
      if (!rule.ownerRule) {
        /* rule is not imported */
      }
    }

This snipped obtains a reference to the stylesheet associated with the `@import` and processes it in some manner:

    let ruleList = document.styleSheets[0].cssRules;

    for (let rule of ruleList) {
      if (rule.ownerRule) {
        checkStylesheet(rule.ownerRule.styleSheet);
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstylesheet-ownerrule">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleSheet.ownerRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`ownerRule`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/ownerRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/ownerRule</a>
