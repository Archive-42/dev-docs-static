&lt;head&gt;: The Document Metadata (Header) element
====================================================

The `<head>` contains machine-readable information ([metadata](https://developer.mozilla.org/en-US/docs/Glossary/Metadata)) about the document, like its [title](title), [scripts](script), and [style sheets](style).

**Note:** `<head>` primarily holds information for machine processing, not human-readability. For human-visible information, like top-level headings and listed authors, see the [`<header>`](header) element.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td><p>If the document is an <a href="iframe"><code>&lt;iframe&gt;</code></a> <a href="iframe#attr-srcdoc"><code>srcdoc</code></a> document, or if title information is available from a higher level protocol (like the subject line in HTML email), zero or more elements of metadata content.</p><p>Otherwise, one or more elements of metadata content where exactly one is a <a href="title"><code>&lt;title&gt;</code></a> element.</p></td></tr><tr class="odd"><td>Tag omission</td><td>The start tag may be omitted if the first thing inside the <code>&lt;head&gt;</code> element is an element.<br />
The end tag may be omitted if the first thing following the <code>&lt;head&gt;</code> element is not a space character or a comment.</td></tr><tr class="even"><td>Permitted parents</td><td>An <a href="html"><code>&lt;html&gt;</code></a> element, as its first child.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadElement"><code>HTMLHeadElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

 `profile` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The [URI](https://developer.mozilla.org/en-US/docs/Glossary/URI)s of one or more metadata profiles, separated by [white space](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace).

Example
-------

    <!doctype html>
    <html>
      <head>
        <title>Document title</title>
      </head>
    </html>

Notes
-----

HTML5-compliant browsers automatically create a `<head>` element if its tags are omitted in the markup. [This auto-creation is not guaranteed in ancient browsers](https://www.stevesouders.com/blog/2010/05/12/autohead-my-first-browserscope-user-test/).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-head-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;head&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from latest shapshot</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/document-metadata.html#the-head-element">HTML5<br />
<span class="small">The definition of '&lt;head&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Obsoleted <code>profile</code></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/global.html#h-7.4.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;head&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`head`

1

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

`profile`

1

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

-   Elements that can be used inside the `<head>`:
    -   [`<title>`](title)
    -   [`<base>`](base)
    -   [`<link>`](link)
    -   [`<style>`](style)
    -   [`<meta>`](meta)
    -   [`<script>`](script)
    -   [`<noscript>`](noscript)
    -   [`<template>`](template)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head</a>
