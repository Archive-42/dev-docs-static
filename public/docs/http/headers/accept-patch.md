Accept-Patch
============

The `Accept-Patch` response HTTP header advertises which media-type the server is able to understand in a PATCH request.

`Accept-Patch` in response to any method means that PATCH is allowed on the resource identified by the Request-URI. Two common cases lead to this:

A server receiving a PATCH request with an unsupported media type could reply with [`415`](../status/415) `Unsupported Media Type` and an Accept-Patch header referencing one or more supported media types.

**Notes:**

-   An IANA registry maintains [a complete list of official content encodings](http://www.iana.org/assignments/http-parameters/http-parameters.xml#http-parameters-1).

-   Two others content encoding, `bzip` and `bzip2`, are sometimes used, though not standard. They implement the algorithm used by these two UNIX programs. Note that the first one was discontinued due to patent licensing problems.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Accept-Patch: application/example, text/example
    Accept-Patch: text/example;charset=utf-8
    Accept-Patch: application/merge-patch+json

Directives
----------

None

Examples
--------

    Accept-Patch: application/example, text/example

    Accept-Patch: text/example;charset=utf-8

    Accept-Patch: application/merge-patch+json

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc5789#section-3.1">RFC 5789, section 3.1: Accept-Patch</a></td><td>HTTP PATCH</td></tr></tbody></table>

Browser compatibility
---------------------

Browser compatibility is not relevant for this header (header is sent by server, and the specification does not define client behaviour).

See also
--------

-   Http method [`PATCH`](../methods/patch)
-   HTTP Semantic and context [RFC 7231, section 4.3.4: PUT](https://tools.ietf.org/html/rfc7231#section-4.3.4)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Patch$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Patch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Patch</a>
