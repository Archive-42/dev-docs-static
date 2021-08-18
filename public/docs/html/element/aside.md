&lt;aside&gt;: The Aside element
================================

The `<aside>` represents a portion of a document whose content is only indirectly related to the document's main content. Asides are frequently presented as sidebars or call-out boxes.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#sectioning_content">sectioning content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#palpable_content">palpable content</a>.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>. Note that an <code>&lt;aside&gt;</code> element must not be a descendant of an <a href="address"><code>&lt;address&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>complementary</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>feed</code>, <code>none</code>, <code>note</code>, <code>presentation</code>, <code>region</code>, <code>search</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

-   Do not use the `<aside>` element to tag parenthesized text, as this kind of text is considered part of the main flow.

Examples
--------

### Using &lt;aside&gt;

This example uses `<aside>` to mark up a paragraph in an article. The paragraph is only indirectly related to the main article content:

    <article>
      <p>
        The Disney movie <cite>The Little Mermaid</cite> was
        first released to theatres in 1989.
      </p>
      <aside>
        <p>
          The movie earned $87 million during its initial release.
        </p>
      </aside>
      <p>
        More info about the movie...
      </p>
    </article>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-aside-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;aside&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sections.html#the-aside-element">HTML5<br />
<span class="small">The definition of '&lt;aside&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`aside`

5

12

4

9

11.1

5

Yes

Yes

4

11.1

4.2

Yes

See also
--------

-   Other section-related elements: [`<body>`](body), [`<article>`](article), [`<section>`](section), [`<nav>`](nav), [`<h1>`](heading_elements), [`<h2>`](heading_elements), [`<h3>`](heading_elements), [`<h4>`](heading_elements), [`<h5>`](heading_elements), [`<h6>`](heading_elements), [`<hgroup>`](hgroup), [`<header>`](header), [`<footer>`](footer), [`<address>`](address);
-   [Using HTML sections and outlines](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines)
-   [ARIA: Complementary role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Complementary_role)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside</a>
