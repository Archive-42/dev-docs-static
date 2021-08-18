Expires
=======

The `Expires` header contains the date/time after which the response is considered stale.

Invalid dates, like the value 0, represent a date in the past and mean that the resource is already expired.

If there is a [`Cache-Control`](cache-control) header with the `max-age` or `s-maxage` directive in the response, the `Expires` header is ignored.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_response_header">CORS-safelisted response header</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Expires: <http-date>

Directives
----------

&lt;http-date&gt;  
An HTTP-date timestamp.

Examples
--------

    Expires: Wed, 21 Oct 2015 07:28:00 GMT

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7234#section-5.3">RFC 7234, section 5.3: Expires</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Caching</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Expires`

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

`Expires`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Cache-Control`](cache-control)
-   [`Age`](age)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Expires$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Expires" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Expires</a>
