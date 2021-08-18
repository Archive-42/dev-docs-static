Host
====

The `Host` request header specifies the host and port number of the server to which the request is being sent.

If no port is included, the default port for the service requested (e.g., `443` for an HTTPS URL, and `80` for an HTTP URL) is implied.

A `Host` header field must be sent in all HTTP/1.1 request messages. A [`400`](../status/400) (Bad Request) status code may be sent to any HTTP/1.1 request message that lacks a `Host` header field or that contains more than one.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Host: <host>:<port>

Directives
----------

&lt;host&gt;  
the domain name of the server (for virtual hosting).

&lt;port&gt; <span class="inlineIndicator optional optionalInline">Optional</span>   
TCP port number on which the server is listening.

Examples
--------

    Host: developer.cdn.mozilla.net

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7230#section-5.4">RFC 7230, section 5.4: Host</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Message Syntax and Routing</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Host`

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

`Host`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`400`](../status/400)
-   [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Host$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Host" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Host</a>
