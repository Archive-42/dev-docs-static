Vary
====

The `Vary` HTTP response header determines how to match future request headers to decide whether a cached response can be used rather than requesting a fresh one from the origin server. It is used by the server to indicate which headers it used when selecting a representation of a resource in a [content negotiation](../content_negotiation) algorithm.

The `Vary` header should be set on a [`304`](../status/304) `Not Modified` response exactly like it would have been set on an equivalent [`200`](../status/200) `OK` response.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Vary: *
    Vary: <header-name>, <header-name>, ...

Directives
----------

\*  
Each request for a URL is supposed to be treated as a unique and uncacheable request. A better way to indicate this is to use [`Cache-Control`](cache-control): `no-store`, which is clearer to read and also signals that the object shouldn't be stored ever.

&lt;header-name&gt;  
A comma-separated list of header names to take into account when deciding whether or not a cached response can be used.

Examples
--------

### Dynamic serving

When using the `Vary: User-Agent` header, caching servers should consider the user agent when deciding whether to serve the page from cache. For example, if you are serving different content to mobile users, it can help you to avoid that a cache may mistakenly serve a desktop version of your site to your mobile users. It can help Google and other search engines to discover the mobile version of a page, and might also tell them that no [Cloaking](https://en.wikipedia.org/wiki/Cloaking) is intended.

    Vary: User-Agent

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-7.1.4">RFC 7231, section 7.1.4: Vary</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Vary`

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

`Vary`

Yes

Yes

Yes

Yes

Yes

Yes

Compatibility notes
-------------------

-   [Vary with care – Vary header problems in IE6-9](https://blogs.msdn.microsoft.com/ieinternals/2009/06/17/vary-with-care/)

See also
--------

-   [Understanding The Vary Header - Smashing Magazine](https://www.smashingmagazine.com/2017/11/understanding-vary-header/)
-   [Best Practices for Using the Vary Header – fastly.com](https://www.fastly.com/blog/best-practices-for-using-the-vary-header)
-   [Content negotiation](https://developer.mozilla.org/docs/Web/HTTP/Content_negotiation)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Vary$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Vary" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Vary</a>
