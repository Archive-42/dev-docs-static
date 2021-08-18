Content-Encoding
================

The `Content-Encoding` entity header is used to compress the media-type. When present, its value indicates which encodings were applied to the entity-body. It lets the client know how to decode in order to obtain the media-type referenced by the `Content-Type` header.

The recommendation is to compress data as much as possible and therefore to use this field, but some types of resources, such as jpeg images, are already compressed. Sometimes, using additional compression doesn't reduce payload size and can even make the payload longer.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Entity_header">Entity header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Content-Encoding: gzip
    Content-Encoding: compress
    Content-Encoding: deflate
    Content-Encoding: identity
    Content-Encoding: br

    // Multiple, in the order in which they were applied
    Content-Encoding: gzip, identity
    Content-Encoding: deflate, gzip

Directives
----------

`gzip`  
A format using the [Lempel-Ziv coding](http://en.wikipedia.org/wiki/LZ77_and_LZ78#LZ77) (LZ77), with a 32-bit CRC. This is the original format of the UNIX *gzip* program. The HTTP/1.1 standard also recommends that the servers supporting this content-encoding should recognize `x-gzip` as an alias, for compatibility purposes.

`compress`  
A format using the [Lempel-Ziv-Welch](http://en.wikipedia.org/wiki/LZW) (LZW) algorithm. The value name was taken from the UNIX *compress* program, which implemented this algorithm. Like the compress program, which has disappeared from most UNIX distributions, this content-encoding is not used by many browsers today, partly because of a patent issue (it expired in 2003).

`deflate`  
Using the [zlib](http://en.wikipedia.org/wiki/Zlib) structure (defined in [RFC 1950](http://tools.ietf.org/html/rfc1950)) with the [*deflate*](http://en.wikipedia.org/wiki/DEFLATE) compression algorithm (defined in [RFC 1951](http://tools.ietf.org/html/rfc1951)).

`identity`  
Indicates the identity function (i.e., no compression or modification). This token, except if explicitly specified, is always deemed acceptable.

`br`  
A format using the [Brotli](https://en.wikipedia.org/wiki/Brotli) algorithm.

Examples
--------

### Compressing with gzip

On the client side, you can advertise a list of compression schemes that will be sent along in an HTTP request. The [`Accept-Encoding`](accept-encoding) header is used for negotiating content encoding.

    Accept-Encoding: gzip, deflate

The server responds with the scheme used, indicated by the `Content-Encoding` response header.

    Content-Encoding: gzip

Note that the server is not obligated to use any compression method. Compression highly depends on server settings and used server modules.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7932">RFC 7932: Brotli Compressed Data Format</a></td><td>Brotli Compressed Data Format</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc7231#section-3.1.2.2">RFC 7231, section 3.1.2.2: Content-Encoding</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc2616#section-14.11">RFC 2616, section 14.11: Content-Encoding</a></td><td>Content-Encoding</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Content-Encoding`

Yes

12

Yes

Yes

Yes

Yes

`br`

50

15

44

No

36

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Content-Encoding`

Yes

Yes

Yes

Yes

Yes

Yes

`br`

51

51

44

No

No

5.0

See also
--------

-   [`Accept-Encoding`](accept-encoding)
-   [`Transfer-Encoding`](transfer-encoding)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding</a>
