# CSSFontFaceRule

The `CSSFontFaceRule` interface represents an [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face) [`at-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule).

## Properties

_Inherits properties from its ancestor [`CSSRule`](cssrule)._

[`CSSFontFaceRule.style`](cssfontfacerule/style)<span class="badge inline readonly">Read only </span>  
Returns a [`CSSStyleDeclaration`](cssstyledeclaration).

## Methods

_Inherits methods from its ancestor [`CSSRule`](cssrule)._

## Examples

This example uses the CSS found as an example on the [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face) page. The first [`CSSRule`](cssrule) returned will be a `CSSFontFaceRule`.

    @font-face {
      font-family: MyHelvetica;
      src: local("Helvetica Neue Bold"),
      local("HelveticaNeue-Bold"),
      url(MgOpenModernaBold.ttf);
      font-weight: bold;
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0]); //a CSSFontFaceRule

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#om-fontface">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'CSSFontFaceRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Supersedes definition in <a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSFontFaceRule">Document Object Model (DOM) Level 2 Style Specification<br />
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

`CSSFontFaceRule`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSFontFaceRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSFontFaceRule</a>
