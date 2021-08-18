&lt;q&gt;: The Inline Quotation element
=======================================

The `<q>` indicates that the enclosed text is a short inline quotation. Most modern browsers implement this by surrounding the text in quotation marks. This element is intended for short quotations that don't require paragraph breaks; for long quotations use the [`<blockquote>`](blockquote) element.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLQuoteElement"><code>HTMLQuoteElement</code></a></td></tr></tbody></table>

**Usage note:** Most modern browsers will automatically add quotation marks around text inside a `<q>` element. A style rule may be needed to add quotation marks in older browsers.

Attributes
----------

This element includes the [global attributes](../global_attributes).

`cite`  
The value of this attribute is a URL that designates a source document or message for the information quoted. This attribute is intended to point to information explaining the context or the reference for the quote.

Example
-------

    <p>According to Mozilla's website,
      <q
      cite="https://www.mozilla.org/en-US/about/history/details/">Firefox 1.0
      was released in 2004 and became a big success.</q></p>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-q-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;q&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-q-element">HTML5<br />
<span class="small">The definition of '&lt;q&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#h-9.2.2">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;q&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`q`

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

-   The [`<blockquote>`](blockquote) element for long quotations.
-   The [`<cite>`](cite) element for source citations.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q</a>
