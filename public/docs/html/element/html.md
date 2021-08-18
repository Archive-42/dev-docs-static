&lt;html&gt;: The HTML Document / Root element
==============================================

The `<html>` represents the root (top-level element) of an HTML document, so it is also referred to as the *root element*. All other elements must be descendants of this element.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td>One <a href="head"><code>&lt;head&gt;</code></a> element, followed by one <a href="body"><code>&lt;body&gt;</code></a> element.</td></tr><tr class="odd"><td>Tag omission</td><td>The start tag may be omitted if the first thing inside the <code>&lt;html&gt;</code> element is not a comment.<br />
The end tag may be omitted if the <code>&lt;html&gt;</code> element is not immediately followed by a comment.</td></tr><tr class="even"><td>Permitted parents</td><td>None. This is the root element of a document.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement"><code>HTMLHtmlElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

 `manifest` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Specifies the [URI](https://developer.mozilla.org/en-US/docs/Glossary/URI) of a resource manifest indicating resources that should be cached locally. See [Using the application cache](../using_the_application_cache) for details.

 `version` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Specifies the version of the HTML [Document Type Definition](https://developer.mozilla.org/en-US/docs/Glossary/Doctype) that governs the current document. This attribute is not needed, because it is redundant with the version information in the document type declaration.

`xmlns`  
Specifies the [XML](https://developer.mozilla.org/en-US/docs/Glossary/XML) [Namespace](https://developer.mozilla.org/en-US/docs/Glossary/Namespace) of the document. Default value is `"http://www.w3.org/1999/xhtml"`. This is required in documents parsed with XML [parsers](https://developer.mozilla.org/en-US/docs/Glossary/Parser), and optional in text/html documents.

Example
-------

    <!DOCTYPE html>
    <html lang="en">
      <head>...</head>
      <body>...</body>
    </html>

Accessibility concerns
----------------------

Providing a [`lang`](../global_attributes#attr-lang) attribute with a [valid IETF identifying language tag](https://www.ietf.org/rfc/bcp/bcp47.txt) on the `<html>` element will help screen reading technology determine the proper language to announce. The identifying language tag should describe the language used by the majority of the content of the page. Without it, screen readers will typically default to the operating system's set language, which may cause mispronunciations.

Including a valid `lang` declaration on the `<html>` element also ensures that important metadata contained in the page's [`<head>`](head), such as the page's [`<title>`](title), are also announced properly.

-   [MDN Understanding WCAG, Guideline 3.1 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Understandable#guideline_3.1_%e2%80%94_readable_make_text_content_readable_and_understandable)
-   [Understanding Success Criterion 3.1.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/meaning-doc-lang-id.html)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-html-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;html&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics.html#the-html-element">HTML5<br />
<span class="small">The definition of '&lt;html&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added support for the <code>manifest</code> attribute (deprecated later).<br />
Obsoleted the <code>version</code> attribute</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/global.html#h-7.3">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;html&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Deprecated the <code>version</code> attribute</td></tr></tbody></table>

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

`html`

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

`manifest`

4

12

3.5-84

3

Versions of Firefox prior to 3.5 ignore the `NETWORK` and `FALLBACK` sections of the cache manifest file.

10

10.6

4

4

18

4-84

11

3.2

1.0

`version`

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

`xmlns`

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

See also
--------

-   MathML top-level element: `<math>`
-   SVG top-level element: [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html</a>
