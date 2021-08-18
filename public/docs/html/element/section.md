&lt;section&gt;: The Generic Section element
============================================

The `<section>` represents a generic standalone section of a document, which doesn't have a more specific semantic element to represent it. Sections should always have a heading, with very few exceptions.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#sectioning_content">Sectioning content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>. Note that a <code>&lt;section&gt;</code> element must not be a descendant of an <a href="address"><code>&lt;address&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>region</code> if the element has an <a href="https://developer.paciellogroup.com/blog/2017/04/what-is-an-accessible-name/">accessible name</a>, otherwise <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">no corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>alert</code>, <code>alertdialog</code>, <code>application</code>, <code>banner</code>, <code>complementary</code>, <code>contentinfo</code>, <code>dialog</code>, <code>document</code>, <code>feed</code>, <code>log</code>, <code>main</code>, <code>marquee</code>, <code>navigation</code>, <code>none</code>, <code>note</code>, <code>presentation</code>, <code>search</code>, <code>status</code>, <code>tabpanel</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

As mentioned above, `<section>` is a generic sectioning element, and should only be used if there isn't a more specific element to represent it. As an example, a navigation menu should be wrapped in a [`<nav>`](nav) element, but a list of search results or a map display and its controls don't have specific elements, and could be put inside a `<section>`.

Also consider these cases:

-   If the contents of the element represent a standalone, atomic unit of content that makes sense syndicated as a standalone piece (e.g. a blog post or blog comment, or a newspaper article), the [`<article>`](article) element would be a better choice.
-   If the contents represent useful tangential information that works alongside the main content, but is not directly part of it (like related links, or an author bio), use an [`<aside>`](aside).
-   If the contents represent the main content area of a document, use [`<main>`](main).
-   If you are only using the element as a styling wrapper, use a [`<div>`](div). A rule of thumb is that a `<section>` should logically appear in the outline of a document.

To reiterate, each `<section>` should be identified, typically by including a heading ([`<h1>`](heading_elements)-[`<h6>`](heading_elements) element) as a child of the `<section>` element, wherever possible. See below for examples of where you might see a `<section>` without a heading.

Examples
--------

### Simple usage example

#### Before

    <div>
      <h2>Heading</h2>
      <p>Bunch of awesome content</p>
    </div>

#### After

    <section>
      <h2>Heading</h2>
      <p>Bunch of awesome content</p>
    </section>

### Using a section without a heading

Circumstances where you might see `<section>` used without a heading are typically found in web application/UI sections rather than in traditional document structures. In a document, it doesn't really make any sense to have a separate section of content without a heading to describe its contents. Such headings are useful for all readers, but particularly useful for users of assistive technologies like screenreaders, and they are also good for SEO.

Consider however a secondary navigation mechanism. If the global navigation is already wrapped in a `<nav>` element, you could conceiveably wrap a previous/next menu in a `<section>`:

    <section>
      <a href="#">Previous article</a>
      <a href="#">Next article</a>
    </section>

Or what about some kind of button bar for controlling your app? This might not necessarily want a heading, but it is still a distinct section of the document:

    <section>
      <button class="reply">Reply</button>
      <button class="reply-all">Reply to all</button>
      <button class="fwd">Forward</button>
      <button class="del">Delete</button>
    </section>

Sections with no headings do not appear in the document outline. If you did want force the inclusion of such an HTML block inside the document outline but not affect the visual output in any way, you could include a heading but hide it:

    <section>
      <h2 class="hidden">Controls</h2>
      <button class="reply">Reply</button>
      <button class="reply-all">Reply to all</button>
      <button class="fwd">Forward</button>
      <button class="del">Delete</button>
    </section>

Make sure to use some assistive technology and screenreader-friendly CSS to hide it, like so:

    .hidden {
      position: absolute;
      top: -9999px;
      left: -9999px;
    }

Depending on the content, including a heading could also be good for SEO, so it is an option to consider.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/sections.html#the-section-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;section&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sections.html#the-section-element">HTML 5.1<br />
<span class="small">The definition of '&lt;section&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/sections.html#the-section-element">HTML5<br />
<span class="small">The definition of '&lt;section&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`section`

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

-   Other section-related elements: [`<body>`](body), [`<nav>`](nav), [`<article>`](article), [`<aside>`](aside), [`<h1>`](heading_elements), [`<h2>`](heading_elements), [`<h3>`](heading_elements), [`<h4>`](heading_elements), [`<h5>`](heading_elements), [`<h6>`](heading_elements), [`<hgroup>`](hgroup), [`<header>`](header), [`<footer>`](footer), [`<address>`](address)
-   [Using HTML sections and outlines](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines)
-   [ARIA: Region role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Region_role)
-   [Why You Should Choose HTML5 article Over section](https://www.smashingmagazine.com/2020/01/html5-article-section/), by Bruce Lawson

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section</a>
