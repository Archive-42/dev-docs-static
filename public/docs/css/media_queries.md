# Media queries

**Media queries** let you adapt your site or app depending on the presence or value of various device characteristics and parameters.

They are a key component of [responsive design](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps). For example, a media query can shrink the font size on small devices, increase the padding between paragraphs when a page is viewed in portrait mode, or bump up the size of buttons on touchscreens.

In [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS), use the [`@media`](@media) [at-rule](at-rule) to conditionally apply part of a style sheet based on the result of a media query. Use [`@import`](@import) to conditionally apply an entire style sheet.

### Media queries in HTML

In [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML), media queries can be applied to various elements:

- In the [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) element's [`media`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link#attr-media) attribute, they define the media to which a linked resource (typically CSS) should be applied.
- In the [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source) element's [`media`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source#attr-media) attribute, they define the media to which that source should be applied. (This is only valid inside [`<picture>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture) elements.)
- In the [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) element's [`media`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style#attr-media) attribute, they define the media to which the style should be applied.

### Media queries in JavaScript

In [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript), you can use the [`Window.matchMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/matchMedia) method to test the window against a media query. You can also use [`MediaQueryList.addListener()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList/addListener) to be notified whenever the state of a query changes. With this functionality, your site or app can respond to changes in the device configuration, orientation, or state.

You can learn more about programmatically using media queries in [Testing media queries](media_queries/testing_media_queries).

## Reference

### At-rules

- [`@import`](@import)
- [`@media`](@media)

## Guides

[Using media queries](media_queries/using_media_queries)  
Introduces media queries, their syntax, and the operators and media features which are used to construct media query expressions.

[Testing media queries programmatically](media_queries/testing_media_queries)  
Describes how to use media queries in your JavaScript code to determine the state of a device, and to set up listeners that notify your code when the results of media queries change (such as when the user rotates the screen or resizes the browser).

[Using Media Queries for Accessibility](media_queries/using_media_queries_for_accessibility)  
Learn how Media Queries can help users understand your website better.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-5/">Media Queries Level 5</a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-conditional-3/">CSS Conditional Rules Module Level 3</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/">Media Queries Level 4</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/">Media Queries</a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/media.html">CSS Level 2 (Revision 1)</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

## See also

- Use [`@supports`](@supports) to apply styles that depend on browser support for various CSS technologies.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries</a>
