Pragma
======

The `Pragma` HTTP/1.0 general header is an implementation-specific header that may have various effects along the request-response chain. It is used for backwards compatibility with HTTP/1.0 caches where the `Cache-Control` HTTP/1.1 header is not yet present.

**Note**: `Pragma` is not specified for HTTP responses and is therefore not a reliable replacement for the general HTTP/1.1 `Cache-Control` header, although it does behave the same as `Cache-Control: no-cache`, if the `Cache-Control` header field is omitted in a request. Use `Pragma` only for backwards compatibility with HTTP/1.0 clients.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/General_header">General header</a>, but response behavior is not specified and thus implementation-specific.</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_response_header">CORS-safelisted response header</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Pragma: no-cache

Directives
----------

no-cache  
Same as `Cache-Control: no-cache`. Forces caches to submit the request to the origin server for validation before releasing a cached copy.

Examples
--------

    Pragma: no-cache

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7234#section-5.4">RFC 7234, section 5.4: Pragma</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Caching</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Pragma`

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

`Pragma`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Pragma$edit" class="_attribution-link">Edit this page on MDN</a>

?? 2005???2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Pragma" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Pragma</a>
