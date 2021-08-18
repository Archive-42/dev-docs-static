&lt;i&gt;: The Idiomatic Text element
=====================================

The `<i>` represents a range of text that is set off from the normal text for some reason, such as idiomatic text, technical terms, taxonomical designations, among others. Historically, these have been presented using italicized type, which is the original source of the `<i>` naming of this element.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

-   Use the `<i>` element for text that is set off from the normal prose for readability reasons. This would be a range of text with different semantic meaning than the surrounding text. Among the use cases for the `<i>` element are spans of text representing a different quality or mode of text, such as:
    -   Alternative voice or mood
    -   Taxonomic designations (such as the genus and species "*Homo sapiens*")
    -   Idiomatic terms from another language (such as "*et cetera*"); these should include the [`lang`](../global_attributes#attr-lang) attribute to identify the language
    -   Technical terms
    -   Transliterations
    -   Thoughts (such as "She wondered, *What is this writer talking about, anyway?*")
    -   Ship or vessel names in Western writing systems (such as "They searched the docks for the *Empress of the Galaxy*, the ship to which they were assigned.")
-   In earlier versions of the HTML specification, the `<i>` element was merely a presentational element used to display text in italics, much like the `<b>` element was used to display text in bold letters. This is no longer true, as these tags now define semantics rather than typographic appearance. A browser will typically still display the contents of the `<i>` element in italic type, but is, by definition, no longer required to do so. To display text in italic type, authors should use the CSS [`font-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style) property.
-   Be sure the text in question is not actually more appropriately marked up with another element.
    -   Use [`<em>`](em) to indicate stress emphasis.
    -   Use [`<strong>`](strong) to indicate importance, seriousness, or urgency.
    -   Use [`<mark>`](mark) to indicate relevance.
    -   Use [`<cite>`](cite) to mark up the name of a work, such as a book, play, or song.
    -   Use [`<dfn>`](dfn) to mark up the defining instance of a term.

Examples
--------

This example demonstrates using the `<i>` element to mark text that is in another language.

    <p>The Latin phrase <i>Veni, vidi, vici</i> is often
    mentioned in music, art, and literature.</p>

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-i-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;i&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-i-element">HTML5<br />
<span class="small">The definition of '&lt;i&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/present/graphics.html#h-15.2.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;b&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`i`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

See also
--------

-   [`<em>`](em)
-   Other italicized elements: [`<var>`](var), [`<dfn>`](dfn), [`<cite>`](cite), [`<address>`](address)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/i" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/i</a>
