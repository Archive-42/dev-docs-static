# CSSImportRule.media

The read-only `media` property of the [`CSSImportRule`](../cssimportrule) interface returns a [`MediaList`](../medialist) object, containing the value of the `media` attribute of the associated stylesheet.

## Syntax

    var media = CSSImportRule.media;

### Value

A [`MediaList`](../medialist) object.

## Examples

The following stylesheet includes a single [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) rule. Therefore the first item in the list of CSS rules will be a `CSSImportRule`. The `media` property returns a [`MediaList`](../medialist) object. This includes the `mediaText` property with a value of `screen`.

    @import url("style.css") screen;

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].media); //returns a MediaList

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssimportrule-media">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSImportRule.media' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No changes from <a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSImportRule">Document Object Model (DOM) Level 2 Style Specification<br />
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

`media`

1

12

1

10

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSImportRule/media" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSImportRule/media</a>
