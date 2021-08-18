Keep-Alive
==========

The `Keep-Alive` general header allows the sender to hint about how the connection may be used to set a timeout and a maximum amount of requests.

The [`Connection`](connection) header needs to be set to "keep-alive" for this header to have any meaning.

Connection-specific header fields such as [`Connection`](connection) and [`Keep-Alive`](keep-alive) are [prohibited in HTTP/2](https://tools.ietf.org/html/rfc7540#section-8.1.2.2). Chrome and Firefox ignore them in HTTP/2 responses, but Safari conforms to the HTTP/2 spec requirements and won’t load any response which contains them.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/General_header">General header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Keep-Alive: parameters

Directives
----------

parameters  
A comma-separated list of parameters, each consisting of an identifier and a value separated by the equal sign (`'='`). The following identifiers are possible:

-   `timeout`: indicating the *minimum* amount of time an idle connection has to be kept opened (in seconds). Note that timeouts longer than the TCP timeout may be ignored if no keep-alive TCP message is set at the transport level.
-   `max`: indicating the maximum number of requests that can be sent on this connection before closing it. Unless `0`, this value is ignored for non-pipelined connections as another request will be sent in the next response. An HTTP pipeline can use it to limit the pipelining.

Examples
--------

A response containing a `Keep-Alive` header:

    HTTP/1.1 200 OK
    Connection: Keep-Alive
    Content-Encoding: gzip
    Content-Type: text/html; charset=utf-8
    Date: Thu, 11 Aug 2016 15:23:13 GMT
    Keep-Alive: timeout=5, max=1000
    Last-Modified: Mon, 25 Jul 2016 04:32:39 GMT
    Server: Apache

    (body)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/draft-thomson-hybi-http-timeout-03#section-2">HTTP Keep-Alive Header</a></td><td>Keep-Alive Header (IETF Internet Draft)</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc7230#appendix-A.1.2">RFC 7230, appendix A.1.2: Keep-Alive</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Message Syntax and Routing</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Keep-Alive`

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

`Keep-Alive`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Connection`](connection)
-   [Connection management in HTTP/1.x](../connection_management_in_http_1.x)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Keep-Alive$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Keep-Alive" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Keep-Alive</a>
