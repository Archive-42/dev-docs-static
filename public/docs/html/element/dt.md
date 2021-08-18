&lt;dt&gt;: The Description Term element
========================================

The `<dt>` specifies a term in a description or definition list, and as such must be used inside a [`<dl>`](dl) element. It is usually followed by a [`<dd>`](dd) element; however, multiple `<dt>` elements in a row indicate several terms that are all defined by the immediate next [`<dd>`](dd) element.

The subsequent [`<dd>`](dd) (**Description Details**) element provides the definition or other related text associated with the term specified using `<dt>`.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, but with no <a href="header"><code>&lt;header&gt;</code></a>, <a href="footer"><code>&lt;footer&gt;</code></a>, sectioning content or heading content descendants.</td></tr><tr class="odd"><td>Tag omission</td><td>The start tag is required. The end tag may be omitted if this element is immediately followed by another <code>&lt;dt&gt;</code> element or a <a href="dd"><code>&lt;dd&gt;</code></a> element, or if there is no more content in the parent element.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="dl"><code>&lt;dl&gt;</code></a> or (in <a href="https://developer.mozilla.org/en-US/docs/Glossary/WHATWG">WHATWG</a> HTML, <a href="https://developer.mozilla.org/en-US/docs/Glossary/W3C">W3C</a> HTML 5.2 and later) a <a href="div"><code>&lt;div&gt;</code></a> that is a child of a <a href="dl"><code>&lt;dl&gt;</code></a>.<br />
This element can be used before a <a href="dd"><code>&lt;dd&gt;</code></a> or another <a href="dt"><code>&lt;dt&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>term</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>listitem</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a> Up to Gecko 1.9.2 (Firefox 4) inclusive, Firefox implements the <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement"><code>HTMLSpanElement</code></a> interface for this element.</td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Examples
--------

For examples, see the [examples provided for the `<dl>` element](dl#examples).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-dt-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;dt&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-dt-element">HTML 5.2<br />
<span class="small">The definition of '&lt;dt&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td><code>&lt;dt&gt;</code> and <code>&lt;dd&gt;</code> elements can now be included in <a href="div"><code>&lt;div&gt;</code></a> elements.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/lists.html#h-10.3">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;dt&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`dt`

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

-   [`<dl>`](dl)
-   [`<dd>`](dd)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dt</a>
