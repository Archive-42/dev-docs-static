Referer
=======

The `Referer` request header contains the address of the page making the request. When following a link, this would be the url of the page containing the link. When making AJAX requests to another domain, this would be your page's url. The `Referer` header allows servers to identify where people are visiting them from and may use that data for analytics, logging, or optimized caching, for example.

**Important**: Although this header has many innocent uses it can have undesirable consequences for user security and privacy. See [Referer header: privacy and security concerns](https://developer.mozilla.org/en-US/docs/Web/Security/Referer_header:_privacy_and_security_concerns) for more information and mitigations.

Note that referer is actually a misspelling of the word "referrer". See [HTTP referer on Wikipedia](https://en.wikipedia.org/wiki/HTTP_referer) for more details.

A `Referer` header is not sent by browsers if:

-   The referring resource is a local "file" or "data" URI.
-   An unsecured HTTP request is used and the referring page was received with a secure protocol (HTTPS).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Referer: <url>

Directives
----------

&lt;url&gt;  
An absolute or partial address of the previous web page from which a link to the currently requested page was followed. URL fragments (i.e. "\#section") and userinfo (i.e. "username:password" in "https://username:password@example.com/foo/bar/") are not included.

Examples
--------

    Referer: https://developer.mozilla.org/en-US/docs/Web/JavaScript

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-5.5.2">RFC 7231, section 5.5.2: Referer</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Referer`

Yes

12

Yes

Yes

Yes

Yes

Length limited to 4096 bytes

77

79

70

No

64

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Referer`

Yes

Yes

Yes

Yes

Yes

Yes

Length limited to 4096 bytes

77

77

No

55

No

No

See also
--------

-   [HTTP referer on Wikipedia](https://en.wikipedia.org/wiki/HTTP_referer)
-   [`Referrer-Policy`](referrer-policy)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer</a>
