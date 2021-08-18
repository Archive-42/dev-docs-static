Digest
======

The `Digest` response HTTP header provides a [digest](https://developer.mozilla.org/en-US/docs/Glossary/digest) of the requested resource.

In [RFC 7231](https://tools.ietf.org/html/rfc7231) terms this is the *selected representation* of a resource. The selected representation depends on the `Content-Type` and `Content-Encoding` header values: so a single resource may have multiple different digest values.

The digest is calculated over the entire representation. The representation itself may be:

-   fully contained in the response message body
-   not at all contained in the message body (for example, in a response to a `HEAD` request)
-   partially contained in the message body (for example, in a response to a [range request](../range_requests)).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Digest: <digest-algorithm>=<digest-value>

    Digest: <digest-algorithm>=<digest-value>,<digest-algorithm>=<digest-value>

Directives
----------

`<digest-algorithm>`  
Supported digest algorithms are defined in [RFC 3230](https://tools.ietf.org/html/rfc3230) and [RFC 5843](https://tools.ietf.org/html/rfc5843), and include `SHA-256` and `SHA-512`. Some of the supported algorithms, including `unixsum` and `MD5` are subject to collisions and are thus not suitable for applications in which collision-resistance is important.

`<digest-value>`  
The result of applying the digest algorithm to the resource representation and encoding the result. The choice of digest algorithm also determines the encoding to use: for example `SHA-256` uses base64 encoding.

Examples
--------

    Digest: sha-256=X48E9qOokqqrvdts8nOJRJN3OWDUoyWxBf7kbu9DBPE=
    Digest: sha-256=X48E9qOokqqrvdts8nOJRJN3OWDUoyWxBf7kbu9DBPE=,unixsum=30637

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

`Digest`

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

`Digest`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Want-Digest`](want-digest)
-   [HTTP range requests](../range_requests)
-   [`206 Partial Content`](../status/206)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Digest$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Digest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Digest</a>
