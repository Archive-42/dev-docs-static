&lt;base&gt;: The Document Base URL element
===========================================

A document's used base URL can be accessed by scripts with [`Node/baseURI`](https://developer.mozilla.org/en-US/docs/Web/API/Node/baseURI). If the document has no `<base>` elements, then `baseURI` defaults to [`location.href`](https://developer.mozilla.org/en-US/docs/Web/API/Location/href).

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>Metadata content.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>There must be no closing tag.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="head"><code>&lt;head&gt;</code></a> that doesn't contain another <a href="base"><code>&lt;base&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseElement"><code>HTMLBaseElement</code></a></td></tr></tbody></table>

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

If either of the following attributes are specified, this element **must** come before other elements with attribute values of URLs, such as [`<link>`](link)’s `href` attribute.

`href`  
The base URL to be used throughout the document for relative URLs. Absolute and relative URLs are allowed.

`target`  
A **keyword** or **author-defined name** of the default [browsing context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context) to show the results of navigation from [`<a>`](a), [`<area>`](area), or [`<form>`](form) elements without explicit `target` attributes.

The following keywords have special meanings:

-   `_self` (default): Show the result in the current browsing context.
-   `_blank`: Show the result in a new, unnamed browsing context.
-   `_parent`: Show the result in the parent browsing context of the current one, if the current page is inside a frame. If there is no parent, acts the same as `_self`.
-   `_top`: Show the result in the topmost browsing context (the browsing context that is an ancestor of the current one and has no parent). If there is no parent, acts the same as `_self`.

Usage notes
-----------

### Multiple &lt;base&gt; elements

If multiple `<base>` elements are used, only the first `href` and first `target` are obeyed — all others are ignored.

### In-page anchors

Links pointing to a fragment in the document — e.g. `<a href="#some-id">` — are resolved with the `<base>`, triggering an HTTP request to the base URL with the fragment attached. For example:

1.  Given `<base href="https://example.com">`
2.  ...and this link: `<a href="#anchor">Anker</a>`
3.  ...the link points to `https://example.com/#anchor`.

### Open Graph

[Open Graph](https://ogp.me/) tags do not acknowledge `<base>`, and should always have full absolute URLs. For example:

    <meta property="og:image" content="https://example.com/thumbnail.jpg">

Examples
--------

    <base href="https://www.example.com/">
    <base target="_blank">
    <base target="_top" href="https://example.com/">

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-base-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;base&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since last snapshot.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/document-metadata#the-base-element">HTML5<br />
<span class="small">The definition of '&lt;base&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Specified the behavior of <code>target</code></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/links.html#h-12.4">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;base&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added the <code>target</code> attribute</td></tr></tbody></table>

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

`base`

Yes

12

1

Yes

Before Internet Explorer 7, `<base>` can be positioned anywhere in the document and the nearest value of `<base>` is used.

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`href`

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

`target`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base</a>
