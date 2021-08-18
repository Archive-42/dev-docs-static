# CSSStyleSheet.rules

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

`rules` is a _deprecated_ _legacy property_ of the [`CSSStyleSheet`](../cssstylesheet) interface. Functionally identical to the preferred [`cssRules`](cssrules) property, it provides access to a live-updating list of the CSS rules comprising the stylesheet.

**Note:** As a legacy property, you not use `rules` and should instead use the preferred [`cssRules`](cssrules). While `rules` is unlikely to be removed soon, its availability is not as widespread and using it will result in compatibility problems for your site or app.

## Syntax

    var rules = cssStyleSheet.rules;

### Value

A live-updating [`CSSRuleList`](../cssrulelist) containing each of the CSS rules making up the stylesheet. Each entry in the rule list is a [`CSSRule`](../cssrule) object describing one rule making up the stylesheet.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstylesheet-rules">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleSheet.rules' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`rules`

1

12

68

9

15

1

1

18

68

14

1

1.0

## See also

- [CSS Object Model](../css_object_model)
- [Using dynamic styling information](../css_object_model/using_dynamic_styling_information)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/rules" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/rules</a>
