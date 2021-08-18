X-Forwarded-Host
================

The `X-Forwarded-Host` (XFH) header is a de-facto standard header for identifying the original host requested by the client in the [`Host`](host) HTTP request header.

Host names and ports of reverse proxies (load balancers, CDNs) may differ from the origin server handling the request, in that case the `X-Forwarded-Host` header is useful to determine which Host was originally used.

This header is used for debugging, statistics, and generating location-dependent content and by design it exposes privacy sensitive information, such as the IP address of the client. Therefore the user's privacy must be kept in mind when deploying this header.

A standardized version of this header is the HTTP [`Forwarded`](forwarded) header.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    X-Forwarded-Host: <host>

Directives
----------

&lt;host&gt;  
The domain name of the forwarded server.

Examples
--------

    X-Forwarded-Host: id42.example-cdn.com

Specifications
--------------

Not part of any current specification. The standardized version of this header is [`Forwarded`](forwarded).

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`X-Forwarded-Host`

?

?

?

?

?

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`X-Forwarded-Host`

?

?

?

?

?

?

See also
--------

-   [`Host`](host)
-   [`Forwarded`](forwarded)
-   [`X-Forwarded-For`](x-forwarded-for)
-   [`X-Forwarded-Proto`](x-forwarded-proto)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-Host$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-Host" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-Host</a>
