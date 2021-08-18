&lt;dd&gt;: The Description Details element
===========================================

The `<dd>` provides the description, definition, or value for the preceding term ([`<dt>`](dt)) in a description list ([`<dl>`](dl)).

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>The start tag is required. The end tag may be omitted if this element is immediately followed by another <code>&lt;dd&gt;</code> element or a <a href="dt"><code>&lt;dt&gt;</code></a> element, or if there is no more content in the parent element.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="dl"><code>&lt;dl&gt;</code></a> or (in <a href="https://developer.mozilla.org/en-US/docs/Glossary/WHATWG">WHATWG</a> HTML, <a href="https://developer.mozilla.org/en-US/docs/Glossary/W3C">W3C</a> HTML 5.2 and later) a <a href="div"><code>&lt;div&gt;</code></a> that is a child of a <a href="dl"><code>&lt;dl&gt;</code></a>.<br />
This element can be used after a <a href="dt"><code>&lt;dt&gt;</code></a> or another <a href="dl"><code>&lt;dl&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>definition</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

 `nowrap` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
If the value of this attribute is set to `yes`, the definition text will not wrap. The default value is `no`.

Examples
--------

For examples, see the [examples provided for the `<dl>` element](dl#examples).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-dd-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;dd&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-dd-element">HTML 5.2<br />
<span class="small">The definition of '&lt;dd&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td><code>&lt;dt&gt;</code> and <code>&lt;dd&gt;</code> elements can now be included in <a href="div"><code>&lt;div&gt;</code></a> elements.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/lists.html#h-10.3">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;dd&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`dd`

Yes

12

1

Before Firefox 4, this element was implemented using the `HTMLSpanElement` interface instead of `HTMLElement`.

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`nowrap`

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
-   [`<dt>`](dt)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dd" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dd</a>
