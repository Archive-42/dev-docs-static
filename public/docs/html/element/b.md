&lt;b&gt;: The Bring Attention To element
=========================================

The `<b>` is used to draw the reader's attention to the element's contents, which are not otherwise granted special importance. This was formerly known as the Boldface element, and most browsers still draw the text in boldface. However, you should not use `<b>` for styling text; instead, you should use the CSS [`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight) property to create boldface text, or the [`<strong>`](strong) element to indicate that text is of special importance.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

-   Use the `<b>` for cases like keywords in a summary, product names in a review, or other spans of text whose typical presentation would be boldfaced (but not including any special importance).
-   Do not confuse the `<b>` element with the [`<strong>`](strong), [`<em>`](em), or [`<mark>`](mark) elements. The [`<strong>`](strong) element represents text of certain *importance*, [`<em>`](em) puts some emphasis on the text and the [`<mark>`](mark) element represents text of certain *relevance*. The `<b>` element doesn't convey such special semantic information; use it only when no others fit.
-   Similarly, do not mark titles and headings using the `<b>` element. For this purpose, use the [`<h1>`](heading_elements) to [`<h6>`](heading_elements) tags. Further, stylesheets can change the default style of these elements, with the result that they are not *necessarily* displayed in bold.
-   It is a good practice to use the [`class`](../global_attributes#attr-class) attribute on the `<b>` element in order to convey additional semantic information as needed (for example `<b class="lead">` for the first sentence in a paragraph). This makes it easier to manage multiple use cases of `<b>` if your stylistic needs change, without the need to change all of its uses in the HTML.
-   Historically, the `<b>` element was meant to make text boldface. Styling information has been deprecated since HTML4, so the meaning of the `<b>` element has been changed.
-   If there is no semantic purpose to using the `<b>` element, you should use the CSS [`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight) property with the value `"bold"` instead in order to make text bold.

Examples
--------

    <p>
      This article describes several <b class="keywords">text-level</b> elements.
      It explains their usage in an <b class="keywords">HTML</b> document.
    </p>
    Keywords are displayed with the default style of the <b>element, likely in bold.</b>

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-b-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;b&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-b-element">HTML5<br />
<span class="small">The definition of '&lt;b&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/present/graphics.html#h-15.2.1">HTML 4.01 Specification<br />
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

`b`

Yes

12

1

Before Firefox 4, this element implemented the `HTMLSpanElement` interface instead of the standard `HTMLElement` interface.

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

-   Other elements conveying [text-level semantics](https://developer.mozilla.org/en-US/docs/Web/HTML/Text_level_semantics_conveying_elements): [`<a>`](a), [`<em>`](em), [`<strong>`](strong), [`<small>`](small), [`<cite>`](cite), [`<q>`](q), [`<dfn>`](dfn), [`<abbr>`](abbr), [`<time>`](time), [`<code>`](code), [`<var>`](var), [`<samp>`](samp), [`<kbd>`](kbd), [`<sub>`](sub), [`<sup>`](sup), [`<i>`](i), [`<mark>`](mark), [`<ruby>`](ruby), [`<rp>`](rp), [`<rt>`](rt), [`<bdo>`](bdo), [`<span>`](span), [`<br>`](br), [`<wbr>`](wbr).
-   [Using &lt;b&gt; and &lt;i&gt; elements (W3C)](https://www.w3.org/International/questions/qa-b-and-i-tags)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/b" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/b</a>
