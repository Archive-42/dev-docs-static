&lt;title&gt;: The Document Title element
=========================================

The **HTML Title element** (`<title>`) defines the document's title that is shown in a [browser](https://developer.mozilla.org/en-US/docs/Glossary/Browser)'s title bar or a page's tab. It only contains text; tags within the element are ignored.

    <title>Grandma's Heavy Metal Festival Journal</title>

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#metadata_content">Metadata content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>Text that is not inter-element <a href="https://developer.mozilla.org/en-US/docs/Glossary/Whitespace">whitespace</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>Both opening and closing tags are required. Note that leaving off <code>&lt;/title&gt;</code> should cause the browser to ignore the rest of the page.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="head"><code>&lt;head&gt;</code></a> element that contains no other <a href="title"><code>&lt;title&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted.</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTitleElement"><code>HTMLTitleElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

The `<title>` element is always used within a page's [`<head>`](head) block.

### Page titles and SEO

The contents of a page title can have significant implications for search engine optimization ([SEO](https://developer.mozilla.org/en-US/docs/Glossary/SEO)). In general, a longer, descriptive title performs better than short or generic titles. The content of the title is one of the components used by search engine algorithms to decide the order in which to list pages in search results. Also, the title is the initial "hook" by which you grab the attention of readers glancing at the search results page.

A few guidelines and tips for composing good titles:

-   Avoid one- or two-word titles. Use a descriptive phrase, or a term-definition pairing for glossary or reference-style pages.
-   Search engines typically display about the first 55–60 characters of a page title. Text beyond that may be lost, so try not to have titles longer than that. If you must use a longer title, make sure the important parts come earlier and that nothing critical is in the part of the title that is likely to be dropped.
-   Don't use "keyword blobs." If your title is just a list of words, algorithms often reduce your page's position in the search results.
-   Try to make sure your titles are as unique as possible within your own site. Duplicate—or near-duplicate—titles can contribute to inaccurate search results.

Example
-------

    <title>Awesome interesting stuff</title>

This example establishes a page whose title (as displayed at the top of the window or in the window's tab) as "Awesome interesting stuff".

Accessibility concerns
----------------------

It is important to provide a `title` value that describes the page's purpose.

A common navigation technique for users of assistive technology is to read the page title and infer the content the page contains. This is because navigating into a page to determine its content can be a time consuming and potentially confusing process.

### Example

    <title>Menu - Blue House Chinese Food - FoodYum: Online takeout today!</title>

To help the user, update the page `title` value to reflect significant page state changes (such as form validation problems).

### Example

    <title>2 errors - Your order - Blue House Chinese Food - FoodYum: Online takeout today!</title>

-   [MDN Understanding WCAG, Guideline 2.4 explanations](#)
-   [Understanding Success Criterion 2.4.2 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-title.html)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-title-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;title&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/document-metadata.html#the-title-element">HTML5<br />
<span class="small">The definition of '&lt;title&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/global.html#h-7.4.2">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;title&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`title`

1

12

1

1

Yes

1

Yes

Yes

4

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title</a>
