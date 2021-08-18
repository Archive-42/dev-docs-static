Content-Range
=============

The `Content-Range` response HTTP header indicates where in a full body message a partial message belongs.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Simple_response_header">CORS-safelisted response-header</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Content-Range: <unit> <range-start>-<range-end>/<size>
    Content-Range: <unit> <range-start>-<range-end>/*
    Content-Range: <unit> */<size>

Directives
----------

&lt;unit&gt;  
The unit in which ranges are specified. This is usually `bytes`.

<!-- -->

&lt;range-start&gt;  
An integer in the given unit indicating the beginning of the request range.

&lt;range-end&gt;  
An integer in the given unit indicating the end of the requested range.

&lt;size&gt;  
The total size of the document (or `'*'` if unknown).

Examples
--------

    Content-Range: bytes 200-1000/67589 

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7233#section-4.2">RFC 7233, section 4.2: Content-Range</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Range Requests</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Content-Range`

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

`Content-Range`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`If-Range`](if-range)
-   [`Range`](range)
-   [`Content-Type`](content-type)
-   [`206`](../status/206) `Partial Content`
-   [`416`](../status/416) `Range Not Satisfiable`

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Range$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Range" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Range</a>
