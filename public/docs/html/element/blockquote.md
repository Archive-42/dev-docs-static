&lt;blockquote&gt;: The Block Quotation element
===============================================

The `<blockquote>` (or *HTML Block Quotation Element*) indicates that the enclosed text is an extended quotation. Usually, this is rendered visually by indentation (see [Notes](#usage_notes) for how to change it). A URL for the source of the quotation may be given using the **cite** attribute, while a text representation of the source can be given using the [`<cite>`](cite) element.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, sectioning root, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLQuoteElement"><code>HTMLQuoteElement</code></a></td></tr></tbody></table>

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

`cite`  
A URL that designates a source document or message for the information quoted. This attribute is intended to point to information explaining the context or the reference for the quote.

Usage notes
-----------

To change the indentation applied to the quoted text, use the [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left) and/or [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right) properties, or the [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) shorthand property.

To include shorter quotes inline rather than in a separate block, use the [`<q>`](q) (Quotation) element.

Example
-------

This example demonstrates the use of the `<blockquote>` element to quote a passage from [RFC 1149](https://tools.ietf.org/html/rfc1149), A Standard for the Transmission of IP Datagrams on Avian Carriers.

    <blockquote cite="https://datatracker.ietf.org/doc/html/rfc1149">
      <p>Avian carriers can provide high delay, low
      throughput, and low altitude service. The
      connection topology is limited to a single
      point-to-point path for each carrier, used with
      standard carriers, but many carriers can be used
      without significant interference with each other,
      outside of early spring. This is because of the 3D
      ether space available to the carriers, in contrast
      to the 1D ether used by IEEE802.3. The carriers
      have an intrinsic collision avoidance system, which
      increases availability.</p>
    </blockquote>

The output from this HTML snippet looks like this:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-blockquote-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;blockquote&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-blockquote-element">HTML5<br />
<span class="small">The definition of '&lt;blockquote&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#h-9.2.2">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;blockquote&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`blockquote`

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

-   The [`<q>`](q) element for inline quotations.
-   The [`<cite>`](cite) element for source citations.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote</a>
