# CSSFontFaceRule.style

The read-only `style` property of the [`CSSFontFaceRule`](../cssfontfacerule) interface returns the style information from the [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face) [at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule). This will be in the form of a [`CSSStyleDeclaration`](../cssstyledeclaration) object.

## Syntax

    var style = CSSFontFaceRule.style;

### Value

A [`CSSStyleDeclaration`](../cssstyledeclaration).

## Examples

This example uses the CSS found as an example on the [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face) page. The first [`CSSRule`](../cssrule) returned will be a `CSSFontFaceRule`. The `style` property returns a [`CSSStyleDeclaration`](../cssstyledeclaration) with the properties `fontFamily`, `fontWeight`, and `src` populated with the information from the rule.

    @font-face {
        font-family: MyHelvetica;
        src: local("Helvetica Neue Bold"),
        local("HelveticaNeue-Bold"),
        url(MgOpenModernaBold.ttf);
        font-weight: bold;
      }

    let myRules = document.styleSheets[0].cssRules;
      console.log(myRules[0].style); //a CSSStyleDeclaration

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#dom-cssfontfacerule-style">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'CSSFontFaceRule.style' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Supersedes definition in <a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSFontFaceRule">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSFontFaceRule' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`style`

1

12

3.5

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSFontFaceRule/style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSFontFaceRule/style</a>
