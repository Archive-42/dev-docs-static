&lt;span&gt;
============

The `<span>` is a generic inline container for phrasing content, which does not inherently represent anything. It can be used to group elements for styling purposes (using the [`class`](../global_attributes#attr-class) or [`id`](../global_attributes#attr-id) attributes), or because they share attribute values, such as [`lang`](../global_attributes#attr-lang). It should be used only when no other semantic element is appropriate. `<span>` is very much like a [`<div>`](div) element, but [`<div>`](div) is a [block-level element](../block-level_elements) whereas a `<span>` is an [inline element](../inline_elements).

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, or any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement"><code>HTMLSpanElement</code></a> (before <a href="https://developer.mozilla.org/en-US/docs/Glossary/HTML5">HTML5</a>, the interface was <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a>)</td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Example
-------

### Example 1

#### HTML

    <p><span>Some text</span></p>

#### Result

### Example 2

#### HTML

    <li><span>
        <a href="portfolio.html" target="_blank">See my portfolio</a>
    </span></li>

#### CSS

    li span {
      background: gold;
     }

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-span-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;span&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-span-element">HTML5<br />
<span class="small">The definition of '&lt;span&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The <a href="https://developer.mozilla.org/en-US/docs/Glossary/DOM">DOM</a> interface is now <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement"><code>HTMLSpanElement</code></a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/global.html#edef-SPAN">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;span&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`span`

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

-   HTML [`<div>`](div) element

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span</a>
