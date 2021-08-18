Transfer-Encoding
=================

The `Transfer-Encoding` header specifies the form of encoding used to safely transfer the [payload body](https://developer.mozilla.org/en-US/docs/Glossary/Payload_body) to the user.

[HTTP/2](https://wikipedia.org/wiki/HTTP/2) doesn't support HTTP 1.1's chunked transfer encoding mechanism, as it provides its own, more efficient, mechanisms for data streaming.

`Transfer-Encoding` is a [hop-by-hop header](../headers#hbh), that is applied to a message between two nodes, not to a resource itself. Each segment of a multi-node connection can use different `Transfer-Encoding` values. If you want to compress data over the whole connection, use the end-to-end [`Content-Encoding`](content-encoding) header instead.

When present on a response to a [`HEAD`](../methods/head) request that has no body, it indicates the value that would have applied to the corresponding [`GET`](../methods/get) message.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Transfer-Encoding: chunked
    Transfer-Encoding: compress
    Transfer-Encoding: deflate
    Transfer-Encoding: gzip
    Transfer-Encoding: identity

    // Several values can be listed, separated by a comma
    Transfer-Encoding: gzip, chunked

Directives
----------

`chunked`  
Data is sent in a series of chunks. The [`Content-Length`](content-length) header is omitted in this case and at the beginning of each chunk you need to add the length of the current chunk in hexadecimal format, followed by '`\r\n`' and then the chunk itself, followed by another '`\r\n`'. The terminating chunk is a regular chunk, with the exception that its length is zero. It is followed by the trailer, which consists of a (possibly empty) sequence of entity header fields.

`compress`  
A format using the [Lempel-Ziv-Welch](http://en.wikipedia.org/wiki/LZW) (LZW) algorithm. The value name was taken from the UNIX *compress* program, which implemented this algorithm.  
Like the compress program, which has disappeared from most UNIX distributions, this content-encoding is used by almost no browsers today, partly because of a patent issue (which expired in 2003).

`deflate`  
Using the [zlib](http://en.wikipedia.org/wiki/Zlib) structure (defined in [RFC 1950](http://tools.ietf.org/html/rfc1950)), with the [*deflate*](http://en.wikipedia.org/wiki/DEFLATE) compression algorithm (defined in [RFC 1951](http://tools.ietf.org/html/rfc1952)).

`gzip`  
A format using the [Lempel-Ziv coding](http://en.wikipedia.org/wiki/LZ77_and_LZ78#LZ77) (LZ77), with a 32-bit CRC. This is originally the format of the UNIX *gzip* program. The HTTP/1.1 standard also recommends that the servers supporting this content-encoding should recognize `x-gzip` as an alias, for compatibility purposes.

`identity`  
Indicates the identity function (i.e. no compression, nor modification). This token, except if explicitly specified, is always deemed acceptable.

Examples
--------

### Chunked encoding

Chunked encoding is useful when larger amounts of data are sent to the client and the total size of the response may not be known until the request has been fully processed. For example, when generating a large HTML table resulting from a database query or when transmitting large images. A chunked response looks like this:

    HTTP/1.1 200 OK 
    Content-Type: text/plain 
    Transfer-Encoding: chunked

    7\r\n
    Mozilla\r\n 
    9\r\n
    Developer\r\n
    7\r\n
    Network\r\n
    0\r\n 
    \r\n

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7230#section-3.3.1">RFC 7230, section 3.3.1: Transfer-Encoding</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Message Syntax and Routing</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Transfer-Encoding`

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

`Transfer-Encoding`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Accept-Encoding`](accept-encoding)
-   [`Content-Encoding`](content-encoding)
-   [`Content-Length`](content-length)
-   Header fields that regulate the use of trailers: [`TE`](te) (requests) and [`Trailer`](trailer) (responses).
-   [Chunked transfer encoding](https://en.wikipedia.org/wiki/Chunked_transfer_encoding)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Transfer-Encoding$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Transfer-Encoding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Transfer-Encoding</a>
