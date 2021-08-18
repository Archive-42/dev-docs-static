Want-Digest
===========

The `Want-Digest` HTTP header is primarily used in a HTTP request, to ask the responder to provide a [digest](https://developer.mozilla.org/en-US/docs/Glossary/digest) of the requested resource using the `Digest` response header.

The header contains identifiers for one or more digest algorithms that the sender wishes the responder to use to create the digest. The sender may use [quality values](https://developer.mozilla.org/en-US/docs/Glossary/Quality_values) to indicate its preference ordering among the choices it offers.

If `Want-Digest` does not include any digest algorithms that the server supports, the server may respond with:

-   a digest calculated using a different digest algorithm, or
-   a `400 Bad Request` error, and include another `Want-Digest` header with that response, listing the algorithms that it does support.

See the page for the `Digest` header for more information.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/General_header">General header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Want-Digest: <digest-algorithm>

    // Multiple algorithms, weighted with the quality value syntax:
    Want-Digest: <digest-algorithm><q-value>,<digest-algorithm><q-value>

Directives
----------

`<digest-algorithm>`  
Supported digest algorithms are defined in [RFC 3230](https://tools.ietf.org/html/rfc3230) and [RFC 5843](https://tools.ietf.org/html/rfc5843), and include `SHA-256` and `SHA-512`. Some of the supported algorithms, including `unixsum` and `MD5` are subject to collisions and are thus not suitable for applications in which collision-resistance is important.

`<q-value>`  
The [quality value](https://developer.mozilla.org/en-US/docs/Glossary/Quality_values) to apply to that option.

Examples
--------

    Want-Digest: sha-256
    Want-Digest: SHA-512;q=0.3, sha-256;q=1, md5;q=0

### Basic operation

The sender provides a list of digests which it is prepared to accept, and the server uses one of them:

    Request:

      GET /item
      Want-Digest: sha-256;q=0.3, sha;q=1

    Response:

      HTTP/1.1 200 Ok
      Digest: sha-256=X48E9qOokqqrvdts8nOJRJN3OWDUoyWxBf7kbu9DBPE=

### Unsupported digests

The server does not support any of the requested digest algorithms, so uses a different algorithm:

    Request:

      GET /item
      Want-Digest: sha;q=1

    Response:

      HTTP/1.1 200 Ok
      Digest: sha-256=X48E9qOokqqrvdts8nOJRJN3OWDUoyWxBf7kbu9DBPE=

The server does not support any of the requested digest algorithms, so responds with a 400 error and includes another `Want-Digest` header, listing the algorithms that it does support:

    Request:

      GET /item
      Want-Digest: sha;q=1

    Response:

      HTTP/1.1 400 Bad Request
      Want-Digest: sha-256, sha-512

Specifications
--------------

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><p><a href="https://datatracker.ietf.org/doc/draft-ietf-httpbis-digest-headers" class="smpl">draft-ietf-httpbis-digest-headers-latest</a></p></td><td>Resource Digests for HTTP</td></tr></tbody></table>

This header was originally defined in [RFC 3230](https://tools.ietf.org/html/rfc3230), but the definition of "selected representation" in [RFC 7231](https://www.rfc-editor.org/info/rfc7231) made the original definition inconsistent with current HTTP specifications. When released, The "Resource Digests for HTTP" draft therefore will obsolete RFC 3230 and will update the standard to be consistent.

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Want-Digest`

Yes

12

Yes

Yes

Yes

Yes

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Want-Digest`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Digest`](digest)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Want-Digest$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Want-Digest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Want-Digest</a>
