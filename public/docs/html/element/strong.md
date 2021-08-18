&lt;strong&gt;: The Strong Importance element
=============================================

The HTML **Strong Importance Element** (`<strong>`) indicates that its contents have strong importance, seriousness, or urgency. Browsers typically render the contents in bold type.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, must have both a start tag and an end tag.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, or any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

The `<strong>` element is for content that is of "strong importance," including things of great seriousness or urgency (such as warnings). This could be a sentence that is of great importance to the whole page, or you could merely try to point out that some words are of greater importance compared to nearby content.

Typically this element is rendered by default using a bold font weight. However, it should *not* be used to apply bold styling; use the CSS [`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight) property for that purpose. Use the [`<b>`](b) element to draw attention to certain text without indicating a higher level of importance. Use the [`<em>`](em) element to mark text that has stress emphasis.

Another accepted use for `<strong>` is to denote the labels of paragraphs which represent notes or warnings within the text of a page.

### &lt;b&gt; vs. &lt;strong&gt;

It is often confusing to new developers why there are so many ways to express the same thing on a rendered website. [`<b>`](b) and `<strong>` are perhaps one of the most common sources of confusion, causing developers to ask "Should I use `<b>` or `<strong>`? Don't they both do the same thing?"

Not exactly. The `<strong>` element is for content that is of greater importance, while the `<b>` element is used to draw attention to text without indicating that it's more important.

It may help to realize that both are valid and semantic elements in HTML5 and that it's a coincidence that they both have the same default styling (boldface) in most browsers (although some older browsers actually underline `<strong>`). Each element is meant to be used in certain types of scenarios, and if you want to bold text for decoration, you should instead actually use the CSS [`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight) property.

The intended meaning or purpose of the enclosed text should be what determines which element you use. Communicating meaning is what semantics are all about.

### &lt;em&gt; vs. &lt;strong&gt;

Adding to the confusion is the fact that while HTML 4 defined `<strong>` as indicating a stronger emphasis, HTML 5 defines `<strong>` as representing "strong importance for its contents." This is an important distinction to make.

While `<em>` is used to change the meaning of a sentence as spoken emphasis does ("I *love* carrots" vs. "I love *carrots*"), `<strong>` is used to give portions of a sentence added importance (e.g., "**Warning!** This is **very dangerous.**") Both `<strong>` and `<em>` can be nested to increase the relative degree of importance or stress emphasis, respectively.

Examples
--------

### Basic example

    <p>Before proceeding, <strong>make sure you put on your safety goggles</strong>.</p>

The resulting output:

### Labeling warnings

    <p><strong>Important:</strong> Before proceeding, make sure you add plenty of butter.</p>

This results in:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-strong-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;strong&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-strong-element">HTML5<br />
<span class="small">The definition of '&lt;strong&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#edef-STRONG">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;strong&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`strong`

1

12

1

Before Firefox 4, creating a `<strong>` element incorrectly resulted in an `HTMLSpanElement` object, instead of the expected `HTMLElement`.

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

-   The [`<b>`](b) element
-   The [`<em>`](em) element
-   The [`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight) property

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong</a>
