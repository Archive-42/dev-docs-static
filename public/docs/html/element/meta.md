&lt;meta&gt;: The metadata element
==================================

The `<meta>` represents [metadata](https://developer.mozilla.org/en-US/docs/Glossary/Metadata) that cannot be represented by other HTML meta-related elements, like [`<base>`](base), [`<link>`](link), [`<script>`](script), [`<style>`](style) or [`<title>`](title).

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#metadata_content">Metadata content</a>. If the <a href="../global_attributes#attr-itemprop"><code>itemprop</code></a> attribute is present: <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>As it is a void element, the start tag must be present and the end tag must not be present.</td></tr><tr class="even"><td>Permitted parents</td><td><ul><li><code>&lt;meta charset&gt;</code>, <code>&lt;meta http-equiv&gt;</code>: a <a href="head"><code>&lt;head&gt;</code></a> element. If the <a href="#attr-http-equiv"><code>http-equiv</code></a> is not an encoding declaration, it can also be inside a <a href="noscript"><code>&lt;noscript&gt;</code></a> element, itself inside a <code>&lt;head&gt;</code> element.</li><li><code>&lt;meta name&gt;</code>: any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#metadata_content">metadata content</a>.</li><li><code>&lt;meta itemprop&gt;</code>: any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#metadata_content">metadata content</a> or <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</li></ul></td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMetaElement"><code>HTMLMetaElement</code></a></td></tr></tbody></table>

The type of metadata provided by the `<meta>` element can be one of the following:

-   If the [`name`](#attr-name) attribute is set, the `<meta>` element provides *document-level metadata*, applying to the whole page.
-   If the [`http-equiv`](#attr-http-equiv) attribute is set, the `<meta>` element is a *pragma directive*, providing information equivalent to what can be given by a similarly-named HTTP header.
-   If the [`charset`](#attr-charset) attribute is set, the `<meta>` element is a *charset declaration*, giving the character encoding in which the document is encoded.
-   If the [`itemprop`](../global_attributes#attr-itemprop) attribute is set, the `<meta>` element provides *user-defined metadata*.

Attributes
----------

This element includes the [global attributes](../global_attributes).

**Note:** the attribute [`name`](#attr-name) has a specific meaning for the `<meta>` element, and the [`itemprop`](../global_attributes#attr-itemprop) attribute must not be set on the same `<meta>` element that has any existing [`name`](#attr-name), [`http-equiv`](#attr-http-equiv) or [`charset`](#attr-charset) attributes.

`charset`  
This attribute declares the document's character encoding. If the attribute is present, its value must be an ASCII case-insensitive match for the string "`utf-8`", because UTF-8 is the only valid encoding for HTML5 documents. `<meta>` elements which declare a character encoding must be located entirely within the first 1024 bytes of the document.

`content`  
This attribute contains the value for the [`http-equiv`](#attr-http-equiv) or [`name`](#attr-name) attribute, depending on which is used.

`http-equiv`  
Defines a pragma directive. The attribute is named `http-equiv(alent)` because all the allowed values are names of particular HTTP headers:

-   `content-security-policy`

    Allows page authors to define a [content policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy) for the current page. Content policies mostly specify allowed server origins and script endpoints which help guard against cross-site scripting attacks.

-   `content-type`

    Declares the [MIME type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types) and character encoding of the document. If specified, the `content` attribute must have the value "`text/html; charset=utf-8`". This is equivalent to a `<meta>` element with the [`charset`](#attr-charset) attribute specified, and carries the same restriction on placement within the document. **Note:** Can only be used in documents served with a `text/html` — not in documents served with an XML MIME type.

-   `default-style`

    Sets the name of the default [CSS style sheet](https://developer.mozilla.org/en-US/docs/Web/CSS) set.

-   `x-ua-compatible`

    If specified, the `content` attribute must have the value "`IE=edge`". User agents are required to ignore this pragma.

-   `refresh` This instruction specifies:

    -   The number of seconds until the page should be reloaded - only if the [`content`](#attr-content) attribute contains a positive integer.
    -   The number of seconds until the page should redirect to another - only if the [`content`](#attr-content) attribute contains a positive integer followed by the string '`;url=`', and a valid URL.

    ##### Accessibility concerns

    Pages set with a `refresh` value run the risk of having the time interval being too short. People navigating with the aid of assistive technology such as a screen reader may be unable to read through and understand the page's content before being automatically redirected. The abrupt, unannounced updating of the page content may also be disorienting for people experiencing low vision conditions.

    -   [MDN Understanding WCAG, Guideline 2.1 explanations](#)
    -   [MDN Understanding WCAG, Guideline 3.1 explanations](#)
    -   [Understanding Success Criterion 2.2.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-required-behaviors.html)
    -   [Understanding Success Criterion 2.2.4 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-postponed.html)
    -   [Understanding Success Criterion 3.2.5 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/consistent-behavior-no-extreme-changes-context.html)

`name`  
The `name` and `content` attributes can be used together to provide document metadata in terms of name-value pairs, with the `name` attribute giving the metadata name, and the `content` attribute giving the value.

See [standard metadata names](meta/name) for details about the set of standard metadata names defined in the HTML specification.

Examples
--------

    <meta charset="utf-8">

    <!-- Redirect page after 3 seconds -->
    <meta http-equiv="refresh" content="3;url=https://www.mozilla.org">

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-meta-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;meta&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`meta`

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

`charset`

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

`content`

1

12

1

≤6

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

`http-equiv`

1

12

1

≤6

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

`name`

1

12

1

≤6

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta</a>
