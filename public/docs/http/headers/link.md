Link
====

The HTTP `Link` entity-header field provides a means for serialising one or more links in HTTP headers. It is semantically equivalent to the HTML [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) element.

Syntax
------

    Link: < uri-reference >; param1=value1; param2="value2"

`<uri-reference>`  
The URI reference, must be enclosed between `<` and `>`.

### Parameters

The link header contains parameters, which are separated with `;` and are equivalent to attributes of the [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) element.

Examples
--------

The URI (absolute or relative) must be enclosed between `<` and `>`:

    Link: <https://example.com>; rel="preconnect"

    Link: https://bad.example; rel="preconnect"

### Specifying multiple links

You can specify multiple links separated by commas, for example:

    Link: <https://one.example.com>; rel="preconnect", <https://two.example.com>; rel="preconnect", <https://three.example.com>; rel="preconnect"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc8288#section-3">RFC 8288, section 3: Link Serialisation in HTTP Headers</a></td><td><span class="spec-RFC">IETF RFC</span></td><td></td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc5988#section-5">RFC 5988, section 5: The Link Header Field</a></td><td><span class="spec-RFC">IETF RFC</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found. Please contribute data for "http.headers.Link" (depth: 1) to the [MDN compatibility data repository](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`103 Early Hints`](../status/103)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Link$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Link" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Link</a>
