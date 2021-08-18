Accept-Encoding
===============

The `Accept-Encoding` request HTTP header advertises which content encoding, usually a compression algorithm, the client is able to understand. Using [content negotiation](../content_negotiation), the server selects one of the proposals, uses it and informs the client of its choice with the [`Content-Encoding`](content-encoding) response header.

Even if both the client and the server supports the same compression algorithms, the server may choose not to compress the body of a response, if the identity value is also acceptable. Two common cases lead to this:

-   The data to be sent is already compressed and a second compression won't lead to smaller data to be transmitted. This may be the case with some image formats;
-   The server is overloaded and cannot afford the computational overhead induced by the compression requirement. Typically, Microsoft recommends not to compress if a server uses more than 80% of its computational power.

As long as the `identity` value, meaning no encoding, is not explicitly forbidden, by an `identity;q=0` or a `*;q=0` without another explicitly set value for identity, the server must never send back a [`406`](../status/406) `Not Acceptable` error.

**Notes:**

-   An IANA registry maintains [a complete list of official content encodings](https://www.iana.org/assignments/http-parameters/http-parameters.xml#http-parameters-1).

-   Two others content encoding, `bzip` and `bzip2`, are sometimes used, though not standard. They implement the algorithm used by these two UNIX programs. Note that the first one was discontinued due to patent licensing problems.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Accept-Encoding: gzip
    Accept-Encoding: compress
    Accept-Encoding: deflate
    Accept-Encoding: br
    Accept-Encoding: identity
    Accept-Encoding: *

    // Multiple algorithms, weighted with the quality value syntax:
    Accept-Encoding: deflate, gzip;q=1.0, *;q=0.5

Directives
----------

`gzip`  
A compression format using the [Lempel-Ziv coding](https://en.wikipedia.org/wiki/LZ77_and_LZ78#LZ77) (LZ77), with a 32-bit CRC.

`compress`  
A compression format using the [Lempel-Ziv-Welch](https://en.wikipedia.org/wiki/LZW) (LZW) algorithm.

`deflate`  
A compression format using the [zlib](https://en.wikipedia.org/wiki/Zlib) structure, with the [*deflate*](https://en.wikipedia.org/wiki/DEFLATE) compression algorithm.

`br`  
A compression format using the [Brotli](https://en.wikipedia.org/wiki/Brotli) algorithm.

`identity`  
Indicates the identity function (i.e. no compression, nor modification). This value is always considered as acceptable, even if not present.

`*`  
Matches any content encoding not already listed in the header. This is the default value if the header is not present. It doesn't mean that any algorithm is supported; merely that no preference is expressed.

 `;q=` (qvalues weighting)  
Any value is placed in an order of preference expressed using a relative [quality value](https://developer.mozilla.org/en-US/docs/Glossary/Quality_values) called *weight*.

Examples
--------

    Accept-Encoding: gzip

    Accept-Encoding: gzip, compress, br

    Accept-Encoding: br;q=1.0, gzip;q=0.8, *;q=0.1

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-5.3.4">RFC 7231, section 5.3.4: Accept-Encoding</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Context</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Accept-Encoding`

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

`Accept-Encoding`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   HTTP [content negotiation](../content_negotiation)
-   Header with the result of the content negotiation: [`Content-Encoding`](content-encoding)
-   Other similar headers: [`TE`](te), [`Accept`](accept), [`Accept-Charset`](accept-charset), [`Accept-Language`](accept-language)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Encoding$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Encoding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Encoding</a>
