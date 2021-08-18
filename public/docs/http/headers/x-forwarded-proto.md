X-Forwarded-Proto
=================

The `X-Forwarded-Proto` (XFP) header is a de-facto standard header for identifying the protocol (HTTP or HTTPS) that a client used to connect to your proxy or load balancer. Your server access logs contain the protocol used between the server and the load balancer, but not the protocol used between the client and the load balancer. To determine the protocol used between the client and the load balancer, the `X-Forwarded-Proto` request header can be used.

A standardized version of this header is the HTTP [`Forwarded`](forwarded) header.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    X-Forwarded-Proto: <protocol>

Directives
----------

&lt;protocol&gt;  
The forwarded protocol (http or https).

Examples
--------

    X-Forwarded-Proto: https

Other non-standard forms:

    # Microsoft
    Front-End-Https: on

    X-Forwarded-Protocol: https 
    X-Forwarded-Ssl: on 
    X-Url-Scheme: https

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

`X-Forwarded-Proto`

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

`X-Forwarded-Proto`

?

?

?

?

?

?

See also
--------

-   [`Forwarded`](forwarded)
-   [`X-Forwarded-For`](x-forwarded-for)
-   [`X-Forwarded-Host`](x-forwarded-host)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-Proto$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-Proto" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-Proto</a>
