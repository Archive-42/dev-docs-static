&lt;u&gt;: The Unarticulated Annotation (Underline) element
===========================================================

The **HTML** **Unarticulated Annotation element** (`<u>`) represents a span of inline text which should be rendered in a way that indicates that it has a non-textual annotation. This is rendered by default as a simple solid underline, but may be altered using CSS.

This element used to be called the "Underline" element in older versions of HTML, and is still sometimes misused in this way. To underline text, you should instead apply a style that includes the CSS [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) property set to `underline`.

See the [Usage notes](#usage_notes) section for further details on when it's appropriate to use `<u>` and when it isn't.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

Along with other pure styling elements, the original HTML Underline (`<u>`) element was deprecated in HTML 4; however, `<u>` was restored in HTML 5 with a new, semantic, meaning: to mark text as having some form of non-textual annotation applied.

Be careful to avoid using the `<u>` element with its default styling (of underlined text) in such a way as to be confused with a hyperlink, which is also underlined by default.

### Use cases

Valid use cases for the `<u>` element include annotating spelling errors, applying a [proper name mark](https://en.wikipedia.org/wiki/Proper_name_mark) to denote proper names in Chinese text, and other forms of annotation.

You should *not* use `<u>` to underline text for presentation purposes, or to denote titles of books.

### Other elements to consider using

In most cases, you should use an element other than `<u>`, such as:

-   [`<em>`](em) to denote stress emphasis
-   [`<b>`](b) to draw attention to text
-   [`<mark>`](mark) to mark key words or phrases
-   [`<strong>`](strong) to indicate that text has strong importance
-   [`<cite>`](cite) to mark the titles of books or other publications
-   [`<i>`](i) to denote technical terms, transliterations, thoughts, or names of vessels in Western texts

To provide textual annotations (as opposed to the non-textual annotations created with `<u>`), use the [`<ruby>`](ruby) element.

To apply an underlined appearance without any semantic meaning, use the [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) property's value `underline`.

Examples
--------

### Indicating a spelling error

This example uses the `<u>` element and some CSS to display a paragraph which includes a misspelled error, with the error indicated in the red wavy underline style which is fairly commonly used for this purpose.

#### HTML

    <p>This paragraph includes a <u class="spelling">wrnogly</u>
    spelled word.</p>

In the HTML, we see the use of `<u>` with a class, `spelling`, which is used to indicate the misspelling of the word "wrongly".

#### CSS

    u.spelling {
      text-decoration: red wavy underline;
    }

This CSS indicates that when the `<u>` element is styled with the class `spelling`, it should have a red wavy underline underneath its text. This is a common styling for spelling errors. Another common style can be presented using `red dashed underline`.

#### Result

The result should be familiar to anyone who has used any of the more popular word processors available today.

### Avoiding &lt;u&gt;

Most of the time, you actually don't want to use `<u>`. Here are some examples that show what you should do instead in several cases.

#### Non-semantic underlines

To underline text without implying any semantic meaning, use a [`<span>`](span) element with the [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) property set to `"underline"`, as shown below.

##### HTML

    <span class="underline">Today's Special</span>
    <br>
    Chicken Noodle Soup With Carrots

##### CSS

    .underline {
      text-decoration: underline;
    }

##### Result

#### Presenting a book title

Book titles should be presented using the [`<cite>`](cite) element instead of `<u>` or even `<i>`.

##### HTML

    <p>The class read <cite>Moby Dick</cite> in the first term.</p>

##### Result with default style

Note that the default styling for the `<cite>` element renders the text in italics. You can, if you wish, override that using CSS:

    cite {
      font-style: normal;
      text-decoration: underline;
    }

##### Result with custom style

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-u-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;u&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-u-element">HTML5<br />
<span class="small">The definition of '&lt;u&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/present/graphics.html#h-15.2.1">HTML 4.01 Specification<br />
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

`u`

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

-   The [`<span>`](span), [`<i>`](i), [`<em>`](em), [`<b>`](b), and [`<cite>`](cite) elements should usually be used instead.
-   The CSS [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) property should be used for non-semantic underlining.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/u" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/u</a>
