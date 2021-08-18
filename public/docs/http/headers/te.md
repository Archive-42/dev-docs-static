TE
==

The `TE` request header specifies the transfer encodings the user agent is willing to accept. (you could informally call it *`Accept-Transfer-Encoding`*, which would be more intuitive).

[In HTTP/2 - the `TE` header field is only accepted if the `trailers` value is set.](https://tools.ietf.org/html/rfc7540#section-8.1.2.2)

See also the [`Transfer-Encoding`](transfer-encoding) response header for more details on transfer encodings. Note that `chunked` is always acceptable for HTTP/1.1 recipients and you don't have to specify `"chunked"` using the `TE` header. However, it is useful for setting if the client is accepting trailer fields in a chunked transfer coding using the "trailers" value.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    TE: compress
    TE: deflate
    TE: gzip
    TE: trailers

    // Multiple directives, weighted with the quality value syntax:
    TE: trailers, deflate;q=0.5

Directives
----------

`compress`  
A format using the [Lempel-Ziv-Welch](http://en.wikipedia.org/wiki/LZW) (LZW) algorithm is accepted as a transfer coding name.

`deflate`  
Using the [zlib](http://en.wikipedia.org/wiki/Zlib) structure is accepted as a transfer coding name.

`gzip`  
A format using the [Lempel-Ziv coding](http://en.wikipedia.org/wiki/LZ77_and_LZ78#LZ77) (LZ77), with a 32-bit CRC is accepted as a transfer coding name.

`trailers`  
Indicates that the client is willing to accept trailer fields in a chunked transfer coding.

`q`  
When multiple transfer codings are acceptable, the `q` parameter of the [quality value](https://developer.mozilla.org/en-US/docs/Glossary/Quality_values) syntax can rank codings by preference.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7230#section-4.3">RFC 7230, section 4.3: TE</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Message Syntax and Routing</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`TE`

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

`TE`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Transfer-Encoding`](transfer-encoding)
-   [`Trailer`](trailer)
-   [Chunked transfer encoding](https://en.wikipedia.org/wiki/Chunked_transfer_encoding)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/TE$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/TE" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/TE</a>
