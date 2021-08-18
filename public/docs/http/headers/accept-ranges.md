Accept-Ranges
=============

The `Accept-Ranges` response HTTP header is a marker used by the server to advertise its support of partial requests. The value of this field indicates the unit that can be used to define a range.

In presence of an `Accept-Ranges` header, the browser may try to *resume* an interrupted download, rather than to start it from the start again.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Accept-Ranges: <range-unit>
    Accept-Ranges: none

Directives
----------

`<range-unit>`  
Defines the range unit the server supports. Though `bytes` is the only range unit formally defined by [RFC 7233](https://tools.ietf.org/html/rfc7233), additional range units may be registered in the [HTTP Range Unit Registry](https://www.iana.org/assignments/http-parameters/http-parameters.xhtml#range-units).

`none`  
No range unit is supported, this makes the header equivalent of its own absence and is therefore rarely used, though some browsers, like IE9, it is used to disable or remove the pause buttons in the download manager.

Examples
--------

    Accept-Ranges: bytes

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7233#section-2.3">RFC 7233, section 2.3: Accept-Ranges</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Range Requests</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Accept-Ranges`

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

`Accept-Ranges`

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
-   [IANA HTTP Range Unit Registry](https://www.iana.org/assignments/http-parameters/http-parameters.xhtml#range-units)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Ranges$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Ranges" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Ranges</a>
