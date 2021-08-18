Set-Cookie2
===========

**Obsolete**  
This feature is obsolete. Although it may still work in some browsers, its use is discouraged since it could be removed at any time. Try to avoid using it.

The obsolete `Set-Cookie2` HTTP response header used to send cookies from the server to the user agent, but has been deprecated by the specification. Use [`Set-Cookie`](set-cookie) instead.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Set-Cookie2: <cookie-name>=<cookie-value> 
    Set-Cookie2: <cookie-name>=<cookie-value>; Comment=<value>
    Set-Cookie2: <cookie-name>=<cookie-value>; CommentURL=<http-url>
    Set-Cookie2: <cookie-name>=<cookie-value>; Discard
    Set-Cookie2: <cookie-name>=<cookie-value>; Domain=<domain-value>
    Set-Cookie2: <cookie-name>=<cookie-value>; Max-Age=<non-zero-digit>
    Set-Cookie2: <cookie-name>=<cookie-value>; Path=<path-value>
    Set-Cookie2: <cookie-name>=<cookie-value>; Port=<port-number>
    Set-Cookie2: <cookie-name>=<cookie-value>; Secure
    Set-Cookie2: <cookie-name>=<cookie-value>; Version=<version-number>

    // Multiple directives are also possible, for example:
    Set-Cookie2: <cookie-name>=<cookie-value>; Domain=<domain-value>; Secure

    // Multiple cookies are seperated by a comma
    Set-Cookie2: <cookie-name>=<cookie-value>, <cookie-name>=<cookie-value>, ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc2965">RFC 2965: Set-Cookie2</a></td><td>Historic specification of HTTP State Management Mechanism, obsoleted by <a href="https://tools.ietf.org/html/rfc6265">RFC 6265</a></td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Set-Cookie2`

No

No

No

No

No

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Set-Cookie2`

No

No

No

No

No

No

See also
--------

-   [`Set-Cookie`](set-cookie)
-   [`Document.cookie`](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie2$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie2" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie2</a>
