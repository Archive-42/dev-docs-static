# CSSImportRule.stylesheet

The read-only `styleSheet` property of the [`CSSImportRule`](../cssimportrule) interface returns the CSS Stylesheet specified by the [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) [at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule). This will be in the form of a [`CSSStyleSheet`](../cssstylesheet) object.

An [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) [at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule) always has an associated stylesheet.

## Syntax

    var href = CSSImportRule.styleSheet;

### Value

A [`CSSStyleSheet`](../cssstylesheet).

## Examples

The following stylesheet includes a single [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) rule. Therefore the first item in the list of CSS rules will be a `CSSImportRule`. The `styleSheet` property returns the imported stylesheet.

    @import url("style.css") screen;

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].styleSheet); //returns a CSSStyleSheet object

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssimportrule-stylesheet">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSImportRule.styleSheet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No changes from <a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSImportRule">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSImportRule' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`stylesheet`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSImportRule/stylesheet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSImportRule/stylesheet</a>
