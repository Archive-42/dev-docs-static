Allow
=====

The `Allow` header lists the set of methods supported by a resource.

This header must be sent if the server responds with a [`405`](../status/405) `Method Not Allowed` status code to indicate which request methods can be used. An empty `Allow` header indicates that the resource allows no request methods, which might occur temporarily for a given resource, for example.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Entity_header">Entity header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Allow: <http-methods>

Directives
----------

&lt;http-methods&gt;  
The comma-separated list of allowed [HTTP request methods](../methods).

Examples
--------

    Allow: GET, POST, HEAD

Specifications
--------------

Specification

Title

[RFC 7231, section 7.4.1: Allow](https://tools.ietf.org/html/rfc7231#section-7.4.1)

Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content

See also
--------

-   [`405`](../status/405)
-   [`Server`](server)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Allow$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Allow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Allow</a>
