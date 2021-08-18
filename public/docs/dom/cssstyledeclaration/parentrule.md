# CSSStyleDeclaration.parentRule

The **CSSStyleDeclaration.parentRule** read-only property returns a [`CSSRule`](../cssrule) that is the parent of this style block, e.g. a [`CSSStyleRule`](../cssstylerule) representing the style for a CSS selector.

## Syntax

    var rule = styles.parentRule;

### Value

The CSS rule that contains this declaration block or `null` if this [`CSSStyleDeclaration`](../cssstyledeclaration) is not attached to a [`CSSRule`](../cssrule).

## Example

The following JavaScript code gets the parent CSS style rule from a [`CSSStyleDeclaration`](../cssstyledeclaration):

    var declaration = document.styleSheets[0].rules[0].style;
    var rule = declaration.parentRule;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstyledeclaration-parentrule">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleDeclaration.parentRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSStyleDeclaration">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSStyleDeclaration' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

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

`parentRule`

1

12

1

9

15

1

4.4

18

4

14

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/parentRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/parentRule</a>
