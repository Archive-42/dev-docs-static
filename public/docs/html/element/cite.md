&lt;cite&gt;: The Citation element
==================================

The **HTML Citation element** (`<cite>`) is used to describe a reference to a cited creative work, and must include the title of that work. The reference may be in an abbreviated form according to context-appropriate conventions related to citation metadata.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a> Up to Gecko 1.9.2 (Firefox 4) inclusive, Firefox implements the <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement"><code>HTMLSpanElement</code></a> interface for this element.</td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

In the context of the `<cite>` element, a creative work that might be cited could be, for example, one of the following:

-   A book
-   A research paper
-   An essay
-   A poem
-   A musical score
-   A song
-   A play or film script
-   A film
-   A television show
-   A game
-   A sculpture
-   A painting
-   A theatrical production
-   A play
-   An opera
-   A musical
-   An exhibition
-   A legal case report
-   A computer program
-   A web site
-   A web page
-   A blog post or comment
-   A forum post or comment
-   A tweet
-   A Facebook post
-   A written or oral statement
-   And so forth.

It's worth noting that the W3C specification says that a reference to a creative work, as included within a `<cite>` element, may include the name of the work’s author. However, the WHATWG specification for `<cite>` says the opposite: that a person’s name must *never* be included, under any circumstances.

To include a reference to the source of quoted material which is contained within a [`<blockquote>`](blockquote) or [`<q>`](q) element, use the [`cite`](blockquote#attr-cite) attribute on the element.

Typically, browsers style the contents of a `<cite>` element in italics by default. To avoid this, apply the CSS [`font-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style) property to the `<cite>` element.

Example
-------

    <p>More information can be found in <cite>[ISO-0000]</cite>.</p>

The HTML above outputs:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-cite-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;cite&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-cite-element">HTML5<br />
<span class="small">The definition of '&lt;cite&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#h-9.2.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;cite&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`cite`

Yes

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

-   The element [`<blockquote>`](blockquote) for long quotations.
-   The element [`<q>`](q) for inline quotations.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/cite" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/cite</a>
