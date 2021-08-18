Accept-Post
===========

The `Accept-Post` response HTTP header advertises which [media types](../basics_of_http/mime_types) are accepted by the server for HTTP post requests.

`Accept-Post` in response to any method means that `POST` is allowed on the requested resource (any document/media format in the header further indicates that the document format is allowed).

For example, a server receiving a `POST` request with an unsupported media type could reply with [`415`](../status/415) `Unsupported Media Type` and an `Accept-Post` header referencing one or more supported media types.

**Notes:**

-   An IANA registry maintains [a complete list of official content encodings](http://www.iana.org/assignments/http-parameters/http-parameters.xml#http-parameters-1).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Accept: <MIME_type>/<MIME_subtype>
    Accept: <MIME_type>/*
    Accept: */*

**Notes:** The `Accept-Post` header specifies a media range in the same way as [`Accept-Language`](accept-language), except that it has no notion of preference (i.e. "accept-params" or "q" arguments are not significant).

Directives
----------

None.

Examples
--------

    Accept-Post: application/example, text/example
    Accept-Post: image/webp
    Accept-Post: */*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/ldp/#header-accept-post">Linked Data Platform 1.0, Section 7.1: The Accept-Post Response Header</a></td><td>ACCEPT POST</td></tr></tbody></table>

Browser compatibility
---------------------

Browser compatibility is not relevant for this header (header is sent by server, and the specification does not define client behaviour).

See also
--------

-   Http method [`POST`](../methods/post)
-   HTTP Semantic and context [RFC 7231, section 4.3.3: POST](https://tools.ietf.org/html/rfc7231#section-4.3.3)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Post$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Post" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Post</a>
