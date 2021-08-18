&lt;h1&gt;–&lt;h6&gt;: The HTML Section Heading elements
========================================================

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, heading content, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>; don't use a heading element as a child of the <a href="hgroup"><code>&lt;hgroup&gt;</code></a> element — it is now deprecated.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/heading_role">heading</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>tab</code>, <code>presentation</code> or <code>none</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement"><code>HTMLHeadingElement</code></a></td></tr></tbody></table>

Attributes
----------

These elements only include the [global attributes](../global_attributes).

The `align` attribute is obsolete; don't use it.

Usage notes
-----------

-   Heading information can be used by user agents to construct a table of contents for a document automatically.
-   Avoid using heading elements to resize text. Instead, use the [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) property.
-   Avoid skipping heading levels: always start from `<h1>`, followed by `<h2>` and so on.
-   Use only one `<h1>` per page or view. It should concisely describe the overall purpose of the content.
-   Using more than one `<h1>` will not result in an error, but is not considered a best practice. Using only one `<h1>` is beneficial for screenreader users, and [SEO](https://developer.mozilla.org/en-US/docs/Glossary/SEO).
-   While HTML5 allows a `<h1>` per [sectioning element](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines#section_elements_in_html5), it is not considered best practice, and may subvert the expectations of how screen reader users navigate.

Examples
--------

### All headings

The following code shows all the heading levels, in use.

    <h1>Heading level 1</h1>
    <h2>Heading level 2</h2>
    <h3>Heading level 3</h3>
    <h4>Heading level 4</h4>
    <h5>Heading level 5</h5>
    <h6>Heading level 6</h6>

Here is the result of this code:

### Example page

The following code shows a few headings with some content under them.

    <h1>Heading elements</h1>
    <h2>Summary</h2>
    <p>Some text here...</p>

    <h2>Examples</h2>
    <h3>Example 1</h3>
    <p>Some text here...</p>

    <h3>Example 2</h3>
    <p>Some text here...</p>

    <h2>See also</h2>
    <p>Some text here...</p>

Here is the result of this code:

Accessibility concerns
----------------------

### Navigation

A common navigation technique for users of screen reading software is jumping from heading to heading to quickly determine the content of the page. Because of this, it is important to not skip one or more heading levels. Doing so may create confusion, as the person navigating this way may be left wondering where the missing heading is.

#### Don't

    <h1>Heading level 1</h1>
    <h3>Heading level 3</h3>
    <h4>Heading level 4</h4>

#### Do

    <h1>Heading level 1</h1>
    <h2>Heading level 2</h2>
    <h3>Heading level 3</h3>

#### Nesting

Headings may be nested as subsections to reflect the organization of the content of the page. Most screen readers can also generate an ordered list of all the headings on a page, which can help a person quickly determine the hierarchy of the content:

1.  `h1` Beetles
    1.  `h2` Etymology
    2.  `h2` Distribution and Diversity
    3.  `h2` Evolution
        1.  `h3` Late Paleozoic
        2.  `h3` Jurassic
        3.  `h3` Cretaceous
        4.  `h3` Cenozoic
    4.  `h2` External Morphology
        1.  `h3` Head
            1.  `h4` Mouthparts
        2.  `h3` Thorax
            1.  `h4` Prothorax
            2.  `h4` Pterothorax
        3.  `h3` Legs
        4.  `h3` Wings
        5.  `h3` Abdomen

When headings are nested, heading levels may be "skipped" when closing a subsection.

-   [Headings • Page Structure • WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/page-structure/headings/)
-   [MDN Understanding WCAG, Guideline 1.3 explanations](#)
-   [Understanding Success Criterion 1.3.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)
-   [MDN Understanding WCAG, Guideline 2.4 explanations](#)
-   [Understanding Success Criterion 2.4.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-skip.html)
-   [Understanding Success Criterion 2.4.6 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-descriptive.html)
-   [Understanding Success Criterion 2.4.10 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-headings.html)

### Labeling section content

Another common navigation technique for users of screen reading software is to generate a list of [sectioning content](../element#content_sectioning) and use it to determine the page's layout.

Sectioning content can be labeled using a combination of the `aria-labelledby` and [`id`](../global_attributes#attr-id) attributes, with the label concisely describing the purpose of the section. This technique is useful for situations where there is more than one sectioning element on the same page.

#### Example

    <header>
      <nav aria-labelledby="primary-navigation">
        <h2 id="primary-navigation">Primary navigation</h2>
        <!-- navigation items -->
      </nav>
    </header>

    <!-- page content -->

    <footer>
      <nav aria-labelledby="footer-navigation">
        <h2 id="footer-navigation">Footer navigation</h2>
        <!-- navigation items -->
      </nav>
    </footer>

In this example, screen reading technology would announce that there are two [`<nav>`](nav) sections, one called "Primary navigation" and one called "Footer navigation". If labels were not provided, the person using screen reading software may have to investigate each `nav` element's contents to determine their purpose.

-   [Using the aria-labelledby attribute](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-labelledby_attribute)
-   [Labeling Regions • Page Structure • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/page-structure/labels/#using-aria-labelledby)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/sections.html#the-h1,-h2,-h3,-h4,-h5,-and-h6-elements">HTML Living Standard<br />
<span class="small">The definition of '&lt;h1&gt;, &lt;h2&gt;, &lt;h3&gt;, &lt;h4&gt;, &lt;h5&gt;, and &lt;h6&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sections.html#the-h1-h2-h3-h4-h5-and-h6-elements">HTML5<br />
<span class="small">The definition of '&lt;h1&gt;, &lt;h2&gt;, &lt;h3&gt;, &lt;h4&gt;, &lt;h5&gt;, and &lt;h6&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/global.html#h-7.5.5">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;h1&gt;, &lt;h2&gt;, &lt;h3&gt;, &lt;h4&gt;, &lt;h5&gt;, and &lt;h6&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`Heading_Elements`

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

-   [`<p>`](p)
-   [`<div>`](div)
-   [`<section>`](section)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements</a>
