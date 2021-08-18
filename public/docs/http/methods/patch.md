PATCH
=====

The `PATCH` applies partial modifications to a resource.

`PATCH` is somewhat analogous to the "update" concept found in [CRUD](https://developer.mozilla.org/en-US/docs/Glossary/CRUD) (in general, HTTP is different than [CRUD](https://developer.mozilla.org/en-US/docs/Glossary/CRUD), and the two should not be confused).

A `PATCH` request is considered a set of instructions on how to modify a resource. Contrast this with [`PUT`](put); which is a complete representation of a resource.

A `PATCH` is not necessarily idempotent, although it can be. Contrast this with [`PUT`](put); which is always idempotent. The word "idempotent" means that any number of repeated, identical requests will leave the resource in the same state. For example if an auto-incrementing counter field is an integral part of the resource, then a [`PUT`](put) will naturally overwrite it (since it overwrites everything), but not necessarily so for `PATCH`.

`PATCH` (like [`POST`](post)) *may* have side-effects on other resources.

To find out whether a server supports `PATCH`, a server can advertise its support by adding it to the list in the [`Allow`](../headers/allow) or [`Access-Control-Allow-Methods`](../headers/access-control-allow-methods) (for [CORS](../cors)) response headers.

Another (implicit) indication that `PATCH` is allowed, is the presence of the [`Accept-Patch`](../headers/accept-patch) header, which specifies the patch document formats accepted by the server.

<table><tbody><tr class="odd"><td>Request has body</td><td>Yes</td></tr><tr class="even"><td>Successful response has body</td><td>Yes</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Safe">Safe</a></td><td>No</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Idempotent">Idempotent</a></td><td>No</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Cacheable">Cacheable</a></td><td>No</td></tr><tr class="even"><td>Allowed in <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms">HTML forms</a></td><td>No</td></tr></tbody></table>

Syntax
------

    PATCH /file.txt HTTP/1.1 

Example
-------

### Request

    PATCH /file.txt HTTP/1.1 
    Host: www.example.com
    Content-Type: application/example
    If-Match: "e0023aa4e"
    Content-Length: 100

    [description of changes]

### Response

A successful response is indicated by any [2xx](https://tools.ietf.org/html/rfc7231#section-6.3) status code.

In the example below a [`204`](../status/204) response code is used, because the response does not carry a payload body. A [`200`](../status/200) response could have contained a payload body.

    HTTP/1.1 204 No Content
    Content-Location: /file.txt
    ETag: "e0023aa4f"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc5789">RFC 5789: PATCH</a></td><td>PATCH Method for HTTP</td></tr></tbody></table>

See also
--------

-   [`204`](../status/204)
-   [`Allow`](../headers/allow), [`Access-Control-Allow-Methods`](../headers/access-control-allow-methods)
-   [`Accept-Patch`](../headers/accept-patch) – specifies the patch document formats accepted by the server.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH</a>
