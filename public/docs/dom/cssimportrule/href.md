# CSSImportRule.href

The read-only `href` property of the [`CSSImportRule`](../cssimportrule) interface returns the URL specified by the [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) [at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule).

The resolved URL will be the [`href`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link#attr-href) attribute of the associated stylesheet.

## Syntax

    var href = CSSImportRule.href;

### Value

A [`USVString`](../usvstring).

## Examples

The following stylesheet includes a single [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) rule. Therefore the first item in the list of CSS rules will be a `CSSImportRule`. The `href` property returns the URL of the imported stylesheet.

    @import url("style.css") screen;

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].href); //returns style.css

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssimportrule-href">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSImportRule.href' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No changes from <a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSImportRule">Document Object Model (DOM) Level 2 Style Specification<br />
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

`href`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSImportRule/href" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSImportRule/href</a>
