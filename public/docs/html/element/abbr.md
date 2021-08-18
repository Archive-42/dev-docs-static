&lt;abbr&gt;: The Abbreviation element
======================================

The **HTML Abbreviation element** (`<abbr>`) represents an abbreviation or acronym; the optional [`title`](../global_attributes#attr-title) attribute can provide an expansion or description for the abbreviation. If present, `title` must contain this full description and nothing else.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a></td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a></td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM Interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only supports the [global attributes](../global_attributes). The [`title`](../global_attributes#attr-title) attribute has a specific semantic meaning when used with the `<abbr>` element; it *must* contain a full human-readable description or expansion of the abbreviation. This text is often presented by browsers as a tooltip when the mouse cursor is hovered over the element.

Each `<abbr>` element you use is independent from all others; providing a `title` for one does not automatically attach the same expansion text to others with the same content text.

Usage notes
-----------

### Typical use cases

It's certainly not required that all abbreviations be marked up using `<abbr>`. There are, though, a few cases where it's helpful to do so:

-   When an abbreviation is used and you want to provide an expansion or definition outside the flow of the document's content, use `<abbr>` with an appropriate [`title`](../global_attributes#attr-title).
-   To define an abbreviation which may be unfamiliar to the reader, present the term using `<abbr>` and either a `title` attribute or inline text providing the definition.
-   When an abbreviation's presence in the text needs to be semantically noted, the `<abbr>` element is useful. This can be used, in turn, for styling or scripting purposes.
-   You can use `<abbr>` in concert with [`<dfn>`](dfn) to establish definitions for terms which are abbreviations or acronyms. See the example [Defining an abbreviation](#defining_an_abbreviation) below.

### Grammar considerations

In languages with [grammatical number](https://en.wikipedia.org/wiki/Grammatical_number) (that is, languages where the number of items affects the grammar of a sentence), use the same grammatical number in your `title` attribute as inside your `<abbr>` element. This is especially important in languages with more than two numbers, such as Arabic, but is also relevant in English.

Default styling
---------------

The purpose of this element is purely for the convenience of the author and all browsers display it inline ([`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)`: inline`) by default, though its default styling varies from one browser to another:

-   Some browsers, like Internet Explorer, do not style it differently than a [`<span>`](span) element.
-   Opera, Firefox, and some others add a dotted underline to the content of the element.
-   A few browsers not only add a dotted underline, but also put it in small caps; to avoid this styling, adding something like [`font-variant`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant)`: none` in the CSS takes care of this case.

Examples
--------

### Marking up an abbreviation semantically

To mark up an abbreviation without providing an expansion or description, use `<abbr>` without any attributes, as seen in this example.

#### HTML

    <p>Using <abbr>HTML</abbr> is fun and easy!</p>

#### Result

### Styling abbreviations

You can use CSS to set a custom style to be used for abbreviations, as seen in this simple example.

#### HTML

    <p>Using <abbr>CSS</abbr>, you can style your abbreviations!</p>

#### CSS

    abbr {
      font-variant: all-small-caps;
    }

#### Result

### Providing an expansion

Adding a [`title`](../global_attributes#attr-title) attribute lets you provide an expansion or definition for the abbreviation or acronym.

#### HTML

    <p>Ashok's joke made me <abbr title="Laugh Out Loud">LOL</abbr> big
    time.</p>

#### Result

### Defining an abbreviation

You can use `<abbr>` in tandem with [`<dfn>`](dfn) to more formally define an abbreviation, as shown here.

#### HTML

    <p><dfn id="html"><abbr title="HyperText Markup Language">HTML</abbr>
    </dfn> is a markup language used to create the semantics and structure
    of a web page.</p>

    <p>A <dfn id="spec">Specification</dfn>
    (<abbr title="Specification">spec</abbr>) is a document that outlines
    in detail how a technology or API is intended to function and how it is
    accessed.</p>

#### Result

Accessibility concerns
----------------------

Spelling out the acronym or abbreviation in full the first time it is used on a page is beneficial for helping people understand it, especially if the content is technical or industry jargon.

#### Example

    <p>JavaScript Object Notation (<abbr>JSON</abbr>) is a lightweight data-interchange format.</p>

This is especially helpful for people who are unfamiliar with the terminology or concepts discussed in the content, people who are new to the language, and people with cognitive concerns.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-abbr-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;abbr&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-abbr-element">HTML5<br />
<span class="small">The definition of '&lt;abbr&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#edef-ABBR">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;abbr&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`abbr`

2

12

1

Before Firefox 4, this element implemented the `HTMLSpanElement` interface instead of the standard `HTMLElement` interface.

7

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

-   [Using the `<abbr>` element](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting#abbreviations)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/abbr" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/abbr</a>
