&lt;wbr&gt;
===========

The `<wbr>` represents a word break opportunity—a position within text where the browser may optionally break a line, though its line-breaking rules would not otherwise create a break at that location.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>Empty</td></tr><tr class="odd"><td>Tag omission</td><td>It is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>; it must have a start tag, but must not have an end tag.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Notes
-----

On UTF-8 encoded pages, `<wbr>` behaves like the `U+200B`` ZERO-WIDTH SPACE` code point. In particular, it behaves like a Unicode bidi BN code point, meaning it has no effect on [bidi](https://developer.mozilla.org/en-US/docs/Glossary/BiDi)-ordering: `<div dir=rtl>123,<wbr>456</div>` displays, when not broken on two lines, `123,456` and not `456,123`.

For the same reason, the `<wbr>` element does not introduce a hyphen at the line break point. To make a hyphen appear only at the end of a line, use the soft hyphen character entity (`&shy;`) instead.

This element was first implemented in Internet Explorer 5.5 and was officially defined in HTML5.

Example
-------

*[The Yahoo Style Guide](https://web.archive.org/web/20121105171040/http://styleguide.yahoo.com/)* recommends [breaking a URL *before* punctuation](https://web.archive.org/web/20121105171040/http://styleguide.yahoo.com/editing/treat-abbreviations-capitalization-and-titles-consistently/website-names-and-addresses), to avoid leaving a punctuation mark at the end of the line, which the reader might mistake for the end of the URL.

    <p>http://this<wbr>.is<wbr>.a<wbr>.really<wbr>.long<wbr>.example<wbr>.com/With<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages</p>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-wbr-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;wbr&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-wbr-element">HTML5<br />
<span class="small">The definition of '&lt;wbr&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`wbr`

1

79

1

5.5-7

11.6

4

Yes

Yes

4

?

?

Yes

See also
--------

-   [`overflow-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap)
-   [`word-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/word-break)
-   [`hyphens`](https://developer.mozilla.org/en-US/docs/Web/CSS/hyphens)
-   The [`<br>`](br) element

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/wbr" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/wbr</a>
