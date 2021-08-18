# LinkStyle

The `LinkStyle` interface provides access to the _associated CSS style sheet_ of a node.

`LinkStyle` is a raw interface and no object of this type can be created; it is implemented by [`HTMLLinkElement`](htmllinkelement) and [`HTMLStyleElement`](htmlstyleelement) objects.

## Properties

_There is no inherited property._

<span class="page-not-created">`LinkStyle.sheet`</span> <span class="badge inline readonly">Read only </span>  
Returns the [`CSSStyleSheet`](cssstylesheet) object associated with the given element, or `null` if there is none.

## Methods

_This interface implements no method._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#the-linkstyle-interface">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'LinkStyle' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td><span class="page-not-created"><code>LinkStyle.sheet</code></span> returns more specialized <a href="cssstylesheet"><code>CSSStyleSheet</code></a> instead of <a href="stylesheet"><code>StyleSheet</code></a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/stylesheets.html#StyleSheets-LinkStyle">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'LinkStyle' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`LinkStyle`

?

≤18

?

?

?

?

?

?

?

?

?

?

`sheet`

?

?

?

?

?

?

?

?

?

?

?

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LinkStyle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LinkStyle</a>
