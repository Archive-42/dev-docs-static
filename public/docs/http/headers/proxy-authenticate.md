Proxy-Authenticate
==================

The HTTP `Proxy-Authenticate` response header defines the authentication method that should be used to gain access to a resource behind a [proxy server](https://developer.mozilla.org/en-US/docs/Glossary/proxy_server). It authenticates the request to the proxy server, allowing it to transmit the request further.

The `Proxy-Authenticate` header is sent along with a [`407`](../status/407) `Proxy Authentication Required`.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Proxy-Authenticate: <type> realm=<realm>

Directives
----------

&lt;type&gt;  
[Authentication type](../authentication#Authentication_schemes). A common type is ["Basic"](../authentication#Basic_authentication_scheme). IANA maintains a [list of authentication schemes](http://www.iana.org/assignments/http-authschemes/http-authschemes.xhtml).

realm=&lt;realm&gt;  
A description of the protected area, the realm. If no realm is specified, clients often display a formatted host name instead.

Examples
--------

    Proxy-Authenticate: Basic

    Proxy-Authenticate: Basic realm="Access to the internal site"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7235#section-4.3">RFC 7235, section 4.3: Proxy-Authenticate</a></td><td>HTTP/1.1: Authentication</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc7617">RFC 7617</a></td><td>The 'Basic' HTTP Authentication Scheme</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Proxy-Authenticate`

1

≤79

1

?

Yes

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Proxy-Authenticate`

37

Yes

Yes

Yes

?

Yes

See also
--------

-   [HTTP authentication](../authentication)
-   [`Authorization`](authorization)
-   [`Proxy-Authorization`](proxy-authorization)
-   [`WWW-Authenticate`](www-authenticate)
-   [`401`](../status/401), [`403`](../status/403), [`407`](../status/407)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Proxy-Authenticate$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Proxy-Authenticate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Proxy-Authenticate</a>
