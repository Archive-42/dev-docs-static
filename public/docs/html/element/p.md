&lt;p&gt;: The Paragraph element
================================

The `<p>` represents a paragraph. Paragraphs are usually represented in visual media as blocks of text separated from adjacent blocks by blank lines and/or first-line indentation, but HTML paragraphs can be any structural grouping of related content, such as images or form fields.

Paragraphs are [block-level elements](../block-level_elements), and notably will automatically close if another block-level element is parsed before the closing `</p>` tag. See “Tag omission” below.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>The start tag is required. The end tag may be omitted if the <a href="p"><code>&lt;p&gt;</code></a> element is immediately followed by an <a href="address"><code>&lt;address&gt;</code></a>, <a href="article"><code>&lt;article&gt;</code></a>, <a href="aside"><code>&lt;aside&gt;</code></a>, <a href="blockquote"><code>&lt;blockquote&gt;</code></a>, <a href="div"><code>&lt;div&gt;</code></a>, <a href="dl"><code>&lt;dl&gt;</code></a>, <a href="fieldset"><code>&lt;fieldset&gt;</code></a>, <a href="footer"><code>&lt;footer&gt;</code></a>, <a href="form"><code>&lt;form&gt;</code></a>, <a href="heading_elements"><code>&lt;h1&gt;</code></a>, <a href="heading_elements"><code>&lt;h2&gt;</code></a>, <a href="heading_elements"><code>&lt;h3&gt;</code></a>, <a href="heading_elements"><code>&lt;h4&gt;</code></a>, <a href="heading_elements"><code>&lt;h5&gt;</code></a>, <a href="heading_elements"><code>&lt;h6&gt;</code></a>, <a href="header"><code>&lt;header&gt;</code></a>, <a href="hr"><code>&lt;hr&gt;</code></a>, <a href="menu"><code>&lt;menu&gt;</code></a>, <a href="nav"><code>&lt;nav&gt;</code></a>, <a href="ol"><code>&lt;ol&gt;</code></a>, <a href="pre"><code>&lt;pre&gt;</code></a>, <a href="section"><code>&lt;section&gt;</code></a>, <a href="table"><code>&lt;table&gt;</code></a>, <a href="ul"><code>&lt;ul&gt;</code></a> or another <a href="p"><code>&lt;p&gt;</code></a> element, or if there is no more content in the parent element and the parent element is not an <a href="a"><code>&lt;a&gt;</code></a> element.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLParagraphElement"><code>HTMLParagraphElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

**Note:** The `align` attribute on `<p>` tags is obsolete and shouldn't be used.

Example
-------

### HTML

    <p>This is the first paragraph of text.
      This is the first paragraph of text.
      This is the first paragraph of text.
      This is the first paragraph of text.</p>
    <p>This is the second paragraph.
      This is the second paragraph.
      This is the second paragraph.
      This is the second paragraph.</p>

### Result

Styling paragraphs
------------------

By default, browsers separate paragraphs with a single blank line. Alternate separation methods, such as first-line indentation, can be achieved with [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS):

### HTML

    <p>Separating paragraphs with blank lines is easiest
    for readers to scan, but they can also be separated
    by indenting their first lines. This is often used
    to take up less space, such as to save paper in print.</p>

    <p>Writing that is intended to be edited, such as school
    papers and rough drafts, uses both blank lines and
    indentation for separation. In finished works, combining
    both is considered redundant and amateurish.</p>

    <p>In very old writing, paragraphs were separated with a
    special character: ¶, the <i>pilcrow</i>. Nowadays, this
    is considered claustrophobic and hard to read.</p>

    <p>How hard to read? See for yourself:
      <button data-toggle-text="Oh no! Switch back!">Use pilcrow for paragraphs</button>
    </p>

### CSS

    p {
      margin: 0;
      text-indent: 3ch;
    }

    p.pilcrow {
       text-indent: 0;
       display: inline;
    }
    p.pilcrow + p.pilcrow::before {
      content: " ¶ ";
    }

### JavaScript

    document.querySelector('button').addEventListener('click', function (event) {
      document.querySelectorAll('p').forEach(function (paragraph) {
        paragraph.classList.toggle('pilcrow');
      });
      var newButtonText = event.target.dataset.toggleText;
      var oldText = event.target.innerText;
      event.target.innerText = newButtonText;
      event.target.dataset.toggleText = oldText;
    });

### Result

Accessibility concerns
----------------------

Breaking up content into paragraphs helps make a page more accessible. Screen-readers and other assistive technology provide shortcuts to let their users skip to the next or previous paragraph, letting them skim content like how white space lets visual users skip around.

Using empty `<p>` elements to add space between paragraphs is problematic for people who navigate with screen-reading technology. Screen readers may announce the paragraph's presence, but not any content contained within it — because there is none. This can confuse and frustrate the person using the screen reader.

If extra space is desired, use [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) properties like [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) to create the effect:

    p {
      margin-bottom: 2em; // increase white space after a paragraph
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-p-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;p&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since the latest <a href="https://developer.mozilla.org/en-US/docs/Glossary/W3C">W3C</a> snapshot <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-p-element">HTML5<br />
<span class="small">The definition of '&lt;p&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td><code>align</code> attribute is obsolete</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#h-9.3.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;p&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`p`

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

-   [`<hr>`](hr)
-   [`<br>`](br)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p</a>
