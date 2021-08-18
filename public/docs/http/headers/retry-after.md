Retry-After
===========

The `Retry-After` response HTTP header indicates how long the user agent should wait before making a follow-up request. There are three main cases this header is used:

-   When sent with a [`503`](../status/503) (Service Unavailable) response, this indicates how long the service is expected to be unavailable.
-   When sent with a [`429`](../status/429) (Too Many Requests) response, this indicates how long to wait before making a new request.
-   When sent with a redirect response, such as [`301`](../status/301) (Moved Permanently), this indicates the minimum time that the user agent is asked to wait before issuing the redirected request.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Retry-After: <http-date>
    Retry-After: <delay-seconds>

Directives
----------

&lt;http-date&gt;  
A date after which to retry. See the [`Date`](date) header for more details on the HTTP date format.

&lt;delay-seconds&gt;  
A non-negative decimal integer indicating the seconds to delay after the response is received.

Examples
--------

### Dealing with scheduled downtime

Support for the `Retry-After` header on both clients and servers is still inconsistent. However, some crawlers and spiders, like the Googlebot, honor the `Retry-After` header. It is useful to send it along with a [`503`](../status/503) (Service Unavailable) response, so that search engines will keep indexing your site when the downtime is over.

    Retry-After: Wed, 21 Oct 2015 07:28:00 GMT
    Retry-After: 120

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-7.1.3">RFC 7231, section 7.1.3: Retry-After</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Retry-After`

?

≤18

No

 No   
See [bug 230260](https://bugzil.la/230260).

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

`Retry-After`

?

?

No

 No   
See [bug 230260](https://bugzil.la/230260).

?

?

?

See also
--------

-   [Google Webmaster blog: How to deal with planned site downtime](https://webmasters.googleblog.com/2011/01/how-to-deal-with-planned-site-downtime.html)
-   [`503`](../status/503) (Service Unavailable)
-   [`301`](../status/301) (Moved Permanently)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Retry-After$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Retry-After" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Retry-After</a>
