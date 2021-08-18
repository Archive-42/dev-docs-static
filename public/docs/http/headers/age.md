Age
===

The `Age` header contains the time in seconds the object has been in a proxy cache.

The `Age` header is usually close to zero. If it is `Age: 0`, it was probably just fetched from the origin server; otherwise It is usually calculated as a difference between the proxy's current date and the [`Date`](date) general header included in the HTTP response.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Age: <delta-seconds>

Directives
----------

&lt;delta-seconds&gt;  
A non-negative integer, representing time in seconds the object has been in a proxy cache.

Examples
--------

    Age: 24

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7234#section-5.1">RFC 7234, section 5.1: Age</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Caching</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Age`

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

`Age`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Cache-Control`](cache-control)
-   [`Expires`](expires)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Age$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Age" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Age</a>
