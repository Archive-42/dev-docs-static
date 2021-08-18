X-Forwarded-For
===============

The `X-Forwarded-For` (XFF) header is a de-facto standard header for identifying the originating IP address of a client connecting to a web server through an HTTP proxy or a load balancer. When traffic is intercepted between clients and servers, server access logs contain the IP address of the proxy or load balancer only. To see the original IP address of the client, the `X-Forwarded-For` request header is used.

This header is used for debugging, statistics, and generating location-dependent content and by design it exposes privacy sensitive information, such as the IP address of the client. Therefore the user's privacy must be kept in mind when deploying this header.

A standardized version of this header is the HTTP [`Forwarded`](forwarded) header.

`X-Forwarded-For` is also an email-header indicating that an email-message was forwarded from another account.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    X-Forwarded-For: <client>, <proxy1>, <proxy2>

Directives
----------

&lt;client&gt;  
The client IP address

&lt;proxy1&gt;, &lt;proxy2&gt;  
If a request goes through multiple proxies, the IP addresses of each successive proxy is listed. This means, the right-most IP address is the IP address of the most recent proxy and the left-most IP address is the IP address of the originating client.

Examples
--------

    X-Forwarded-For: 2001:db8:85a3:8d3:1319:8a2e:370:7348

    X-Forwarded-For: 203.0.113.195

    X-Forwarded-For: 203.0.113.195, 70.41.3.18, 150.172.238.178

Other non-standard forms:

    # Used for some Google services
    X-ProxyUser-Ip: 203.0.113.19

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

`X-Forwarded-For`

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

`X-Forwarded-For`

?

?

?

?

?

?

See also
--------

-   [`Forwarded`](forwarded)
-   [`X-Forwarded-Host`](x-forwarded-host)
-   [`X-Forwarded-Proto`](x-forwarded-proto)
-   [`Via`](via)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-For$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-For" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-For</a>
