X-Content-Type-Options
======================

The `X-Content-Type-Options` response HTTP header is a marker used by the server to indicate that the [MIME types](../basics_of_http/mime_types) advertised in the [`Content-Type`](content-type) headers should not be changed and be followed. This is a way to opt out of [MIME type sniffing](../basics_of_http/mime_types#MIME_sniffing), or, in other words, to say that the MIME types are deliberately configured.

This header was introduced by Microsoft in IE 8 as a way for webmasters to block content sniffing that was happening and could transform non-executable MIME types into executable MIME types. Since then, other browsers have introduced it, even if their MIME sniffing algorithms were less aggressive.

Starting with Firefox 72, the opting out of MIME sniffing is also applied to top-level documents if a [`Content-type`](content-type) is provided. This can cause HTML web pages to be downloaded instead of being rendered when they are served with a MIME type other than `text/html`. Make sure to set both headers correctly.

Site security testers usually expect this header to be set.

Note: `X-Content-Type-Options` only apply [request-blocking due to `nosniff`](https://fetch.spec.whatwg.org/#should-response-to-request-be-blocked-due-to-nosniff?) for [request destinations](https://fetch.spec.whatwg.org/#concept-request-destination) of "`script`" and "`style`". However, it also [enables Cross-Origin Read Blocking (CORB)](https://chromium.googlesource.com/chromium/src/+/master/services/network/cross_origin_read_blocking_explainer.md#determining-whether-a-response-is-corb_protected) protection for HTML, TXT, JSON and XML files (excluding SVG `image/svg+xml`).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    X-Content-Type-Options: nosniff

Directives
----------

`nosniff`  
Blocks a request if the request destination is of type:

-   "`style`" and the MIME type is not `text/css`, or
-   "`script`" and the MIME type is not a [JavaScript MIME type](https://html.spec.whatwg.org/multipage/scripting.html#javascript-mime-type)

Enables Cross-Origin Read Blocking (CORB) protection for the MIME-types:

-   `text/html`
-   `text/plain`
-   `text/json`, `application/json` or any other type with a JSON extension: `*/*+json`
-   `text/xml`, `application/xml` or any other type with an XML extension: `*/*+xml` (excluding `image/svg+xml`)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#x-content-type-options-header">Fetch<br />
<span class="small">The definition of 'X-Content-Type-Options definition' in that specification.</span></a></td><td><span class="spec-Living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`X-Content-Type-Options`

64

 64  
1   
Not supported for stylesheets.

12

50

8

Yes

11

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`X-Content-Type-Options`

64

 64  
Partial   
Not supported for stylesheets.

64

 64  
Partial   
Not supported for stylesheets.

50

Yes

11

9.0

 9.0  
Partial   
Not supported for stylesheets.

### Browser specific notes

-   Firefox 72 enables `X-Content-Type-Options: nosniff` for top-level documents

See also
--------

-   [`Content-Type`](content-type)
-   The [original definition](https://blogs.msdn.microsoft.com/ie/2008/09/02/ie8-security-part-vi-beta-2-update/) of X-Content-Type-Options by Microsoft.
-   The [Mozilla Observatory](https://observatory.mozilla.org/) tool testing the configuration (including this header) of Web sites for safety and security
-   [Mitigating MIME Confusion Attacks in Firefox](https://blog.mozilla.org/security/2016/08/26/mitigating-mime-confusion-attacks-in-firefox/)
-   [Cross-Origin Read Blocking (CORB)](https://fetch.spec.whatwg.org/#corb)
-   [Google Docs CORB explainer](https://chromium.googlesource.com/chromium/src/+/master/services/network/cross_origin_read_blocking_explainer.md)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Content-Type-Options$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Content-Type-Options" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Content-Type-Options</a>
