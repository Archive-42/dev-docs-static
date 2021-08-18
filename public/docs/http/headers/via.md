Via
===

The `Via` general header is added by proxies, both forward and reverse proxies, and can appear in the request headers and the response headers. It is used for tracking message forwards, avoiding request loops, and identifying the protocol capabilities of senders along the request/response chain.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/General_header">General header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Via: [ <protocol-name> "/" ] <protocol-version> <host> [ ":" <port> ]
    or
    Via: [ <protocol-name> "/" ] <protocol-version> <pseudonym>

Directives
----------

&lt;protocol-name&gt;  
Optional. The name of the protocol used, such as "HTTP".

&lt;protocol-version&gt;  
The version of the protocol used, such as "1.1".

&lt;host&gt; and &lt;port&gt;  
Public proxy URL and port.

&lt;pseudonym&gt;  
Name/alias of an internal proxy.

Examples
--------

    Via: 1.1 vegur
    Via: HTTP/1.1 GWA
    Via: 1.0 fred, 1.1 p.example.net

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7230#section-5.7.1">RFC 7230, section 5.7.1: Via</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Message Syntax and Routing</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Via`

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

`Via`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`X-Forwarded-For`](x-forwarded-for)
-   [Heroku's proxy library Vegur](https://github.com/heroku/vegur)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Via$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Via" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Via</a>
