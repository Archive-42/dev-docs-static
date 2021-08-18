Trailer
=======

The **Trailer** response header allows the sender to include additional fields at the end of chunked messages in order to supply metadata that might be dynamically generated while the message body is sent, such as a message integrity check, digital signature, or post-processing status.

The [`TE`](te) request header needs to be set to "trailers" to allow trailer fields.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Trailer: header-names

Directives
----------

`header-names`  
HTTP header fields which will be present in the trailer part of chunked messages. These header fields are **disallowed**:

-   message framing headers (e.g., [`Transfer-Encoding`](transfer-encoding) and [`Content-Length`](content-length)),
-   routing headers (e.g., [`Host`](host)),
-   request modifiers (e.g., controls and conditionals, like [`Cache-Control`](cache-control), [`Max-Forwards`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Max-Forwards), or [`TE`](te)),
-   authentication headers (e.g., [`Authorization`](authorization) or [`Set-Cookie`](set-cookie)),
-   or [`Content-Encoding`](content-encoding), [`Content-Type`](content-type), [`Content-Range`](content-range), and `Trailer` itself.

Examples
--------

### Chunked transfer encoding using a trailing header

In this example, the [`Expires`](expires) header is used at the end of the chunked message and serves as a trailing header.

    HTTP/1.1 200 OK 
    Content-Type: text/plain 
    Transfer-Encoding: chunked
    Trailer: Expires

    7\r\n 
    Mozilla\r\n 
    9\r\n 
    Developer\r\n 
    7\r\n 
    Network\r\n 
    0\r\n 
    Expires: Wed, 21 Oct 2015 07:28:00 GMT\r\n
    \r\n

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7230#section-4.4">RFC 7230, section 4.4: Trailer</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Message Syntax and Routing</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc7230#section-4.1.2">RFC 7230, section 4.1.2: Chunked trailer part</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Message Syntax and Routing</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Trailer`

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

`Trailer`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Transfer-Encoding`](transfer-encoding)
-   [`TE`](te)
-   [Chunked transfer encoding](https://en.wikipedia.org/wiki/Chunked_transfer_encoding)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Trailer$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Trailer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Trailer</a>
