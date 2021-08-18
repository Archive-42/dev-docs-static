Location
========

The `Location` response header indicates the URL to redirect a page to. It only provides a meaning when served with a `3xx` (redirection) or `201` (created) status response.

In cases of redirection, the HTTP method used to make the new request to fetch the page pointed to by `Location` depends of the original method and of the kind of redirection:

-   If [`303`](../status/303) (See Also) responses always lead to the use of a [`GET`](../methods/get) method, [`307`](../status/307) (Temporary Redirect) and [`308`](../status/308) (Permanent Redirect) don't change the method used in the original request;
-   [`301`](../status/301) (Permanent Redirect) and [`302`](../status/302) (Found) doesn't change the method most of the time, though older user-agents may (so you basically don't know).

All responses with one of these status codes send a `Location` header.

In cases of resource creation, it indicates the URL to the newly created resource.

`Location` and [`Content-Location`](content-location) are different: `Location` indicates the target of a redirection (or the URL of a newly created resource), while [`Content-Location`](content-location) indicates the direct URL to use to access the resource when [content negotiation](../content_negotiation) happened, without the need of further content negotiation. `Location` is a header associated with the response, while [`Content-Location`](content-location) is associated with the entity returned.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Location: <url>

Directives
----------

&lt;url&gt;  
A relative (to the request URL) or absolute URL.

Examples
--------

    Location: /index.html

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-7.1.2">RFC 7231, section 7.1.2: Location</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Location`

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

`Location`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Content-Location`](content-location)
-   Status of responses including a `Location` header: [`201`](../status/201), [`301`](../status/301), [`302`](../status/302), [`303`](../status/303), [`307`](../status/307), [`308`](../status/308).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Location$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Location" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Location</a>
