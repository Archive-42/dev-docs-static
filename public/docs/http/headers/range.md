Range
=====

The `Range` HTTP request header indicates the part of a document that the server should return. Several parts can be requested with one `Range` header at once, and the server may send back these ranges in a multipart document. If the server sends back ranges, it uses the [`206`](../status/206)` Partial Content` for the response. If the ranges are invalid, the server returns the [`416`](../status/416)` Range Not Satisfiable` error. The server can also ignore the `Range` header and return the whole document with a [`200`](../status/200) status code.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Range: <unit>=<range-start>-
    Range: <unit>=<range-start>-<range-end>
    Range: <unit>=<range-start>-<range-end>, <range-start>-<range-end>
    Range: <unit>=<range-start>-<range-end>, <range-start>-<range-end>, <range-start>-<range-end>
    Range: <unit>=-<suffix-length>

Directives
----------

&lt;unit&gt;  
The unit in which ranges are specified. This is usually `bytes`.

<!-- -->

&lt;range-start&gt;  
An integer in the given unit indicating the beginning of the request range.

&lt;range-end&gt;  
An integer in the given unit indicating the end of the requested range. This value is optional and, if omitted, the end of the document is taken as the end of the range.

&lt;suffix-length&gt;  
An integer in the given unit indicating the number of units at the end of the file to return.

Examples
--------

Requesting three ranges from the file.

    Range: bytes=200-1000, 2000-6576, 19000- 

Requesting the first 500 and last 500 bytes of the file. The request may be rejected by the server if the ranges overlap.

    Range: bytes=0-499, -500 

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7233#section-3.1">RFC 7233, section 3.1: Range</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Range Requests</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Range`

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

`Range`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`If-Range`](if-range)
-   [`Content-Range`](content-range)
-   [`Content-Type`](content-type)
-   [`206`](../status/206)` Partial Content`
-   [`416`](../status/416)` Range Not Satisfiable`

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Range$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Range" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Range</a>
