&lt;bdo&gt;: The Bidirectional Text Override element
====================================================

The **HTML Bidirectional Text Override element** (`<bdo>`) overrides the current directionality of text, so that the text within is rendered in a different direction.

The text's characters are drawn from the starting point in the given direction; the individual characters' orientation is not affected (so characters don't get drawn backward, for example).

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a> Up to Gecko 1.9.2 (Firefox 4) inclusive, Firefox implements the <code>HTMLSpanElement</code> interface for this element.</td></tr></tbody></table>

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

`dir`  
The direction in which text should be rendered in this element's contents. Possible values are:

-   `ltr`: Indicates that the text should go in a left-to-right direction.
-   `rtl`: Indicates that the text should go in a right-to-left direction.

Examples
--------

    <!-- Switch text direction -->
    <p>This text will go left to right.</p>
    <p><bdo dir="rtl">This text will go right
    to left.</bdo></p>

### Result

Notes
-----

The HTML 4 specification did not specify events for this element; they were added in XHTML. This is most likely an oversight.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-bdo-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;bdo&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-bdo-element">HTML5<br />
<span class="small">The definition of '&lt;bdo&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/dirlang.html#h-8.2.4">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;bdo&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`bdo`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   Related HTML element: [`<bdi>`](bdi)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/bdo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/bdo</a>
